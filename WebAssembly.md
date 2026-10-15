**WebAssembly (Wasm)** is a low-level binary instruction format for a sandboxed stack-based virtual machine. It is a *compilation target*: code written in C, C++, Rust, Go and others is compiled to a `.wasm` module and runs in the browser (or elsewhere) at near-native speed, alongside JavaScript.

You rarely write it by hand. The human-readable text format (`.wat`) exists mostly for debugging.

### Core properties

| Property | What it means |
| --- | --- |
| Compact binary | Typed instructions the engine can decode and compile quickly |
| Predictable performance | No GC pauses unless the module opts into WasmGC |
| Sandboxed | Sees only its own *linear memory* and the functions the host imports into it. No direct DOM, file or network access |
| Host-agnostic | Runs in browsers and in standalone runtimes |

### Working with JavaScript

JS loads the module, provides the imports and calls its exports:

```js
const { instance } = await WebAssembly.instantiateStreaming(fetch('x.wasm'), imports)
instance.exports.doWork()
```

The usual split: **Wasm does the heavy computation, JS owns the UI and browser APIs.** Calls between the two have overhead, so put work in Wasm in large chunks, not many small calls.

### Outside the browser

- **WASI** (WebAssembly System Interface) gives modules a standard, capability-based way to reach files, clocks and other system resources.
- Runtimes: Wasmtime, WasmEdge, Wasmer.
- Uses: edge compute (Cloudflare Workers, Fastly), plugin systems (Envoy, databases, editors).
- The **Component Model** adds language-neutral interfaces, so modules written in different languages can work together.

### When to use / when not

| Good fit | Poor fit |
| --- | --- |
| Image/video/audio processing (Squoosh, ffmpeg.wasm) | Ordinary UI or DOM-heavy code |
| Games and engines (Unity, Unreal) | App logic that JS engines already run fast |
| CAD/design tools (Figma, AutoCAD web) | Many small JS↔Wasm calls |
| Running existing native code in the browser (Pyodide, SQLite, [[Typst]]) | Cases where the download size of a large module matters more than speed |

### Related

- [[Typst]], whose compiler is shipped as Wasm to typeset documents in the browser
- [[Stack based and Heap Based allocations]]

## References

- https://webassembly.org
- https://wasi.dev
- MDN: https://developer.mozilla.org/en-US/docs/WebAssembly
