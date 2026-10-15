**Typst** is a markup-based typesetting system written in Rust and positioned as a modern alternative to LaTeX. It has a readable syntax, a real scripting language (variables, functions, loops, `json()`/`csv()` loading), fast incremental compilation and clear error messages.

Because the compiler is Rust, it can be compiled to [[WebAssembly]] and run entirely in the browser, with no server and no TeX installation.

### Core idea

A `.typ` file mixes content and code:

```typst
#let data = json("/data.json")
#if data.template == "minimal" { minimal.render(data) } else { two-column.render(data) }
```

This makes it a good **template engine for documents**: keep the data as JSON, keep the layout in Typst, and the compiler outputs PDF, SVG or PNG.

### Running it in the browser: typst.ts

`typst.ts` (`@myriaddreamin/typst.ts`) wraps Typst's Wasm builds:

| Package | Role |
| --- | --- |
| `typst-ts-web-compiler` | Wasm compiler: sources → document (vector format or PDF bytes) |
| `typst-ts-renderer` | Wasm renderer: vector document → SVG (or canvas) |
| `typst.ts` | JS API: `createTypstCompiler`, `createTypstRenderer`, font builder |

Key mechanics:

- **Virtual filesystem.** `compiler.addSource(path, text)` adds `.typ` files and `compiler.mapShadow(path, bytes)` injects data such as `/data.json` or images.
- **Fonts are explicit.** Pass `loadFonts([], { assets: false })` to stop typst.ts from downloading default fonts from a CDN, then add your own TTFs through the font builder. Bundling the exact font files is what makes the output **identical on every device**.
- **One compile at a time.** The compiler holds shared state (sources, fonts, shadow files), so queue the jobs.
- **Lazy-load.** The Wasm is large, so load it on the first render and keep the engine in memory afterwards.
- **Renderer quirk.** The SVG size gets rounded up to whole points (an A4 page is 595.28pt wide but comes out as 596pt), which leaves a blank strip along the edges. Rewrite `viewBox`/`width`/`height` to the exact page size.

### Pattern: one engine for preview and export

Example from the `resume-builder` project:

1. JS turns the domain data (a JSON Resume) into a small set of generic section "kinds" (`text`, `contact`, `links`, `entries`, `tags`, `languages`). Templates only need to know how to draw those few kinds.
2. That JSON is written to `/data.json`, and `main.typ` passes it to the chosen layout template. Shared drawing helpers live in `lib.typ`.
3. Compiling in **vector** format gives the SVG for the live preview. Compiling in **PDF** format gives the bytes for download.

Since one engine produces both, the **preview and the PDF always match**.

### When to use / when not

| Good fit | Poor fit |
| --- | --- |
| Generated documents from data (resumes, invoices, reports) | Pixel-exact HTML/CSS reuse |
| Client-side PDF export without a server | Very bundle-size-sensitive pages |
| Math/scientific writing as a lighter LaTeX | Workflows locked into LaTeX packages/journals |

### Related

- [[WebAssembly]]

## References

- https://typst.app/docs
- https://github.com/Myriad-Dreamin/typst.ts
