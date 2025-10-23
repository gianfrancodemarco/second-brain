
### [[asyncIO]]

FastAPI is built **on top of `asyncio`**.  
It uses asynchronous I/O to handle thousands of concurrent network requests efficiently.  
Every `async def` route in FastAPI is an **asyncio coroutine** scheduled by an **event loop** (usually `uvloop` or the standard library’s `asyncio` loop)

##### Execution Model

1. A FastAPI application runs inside an [[ASGI and WSGI||ASGI]] (e.g. `uvicorn`, `hypercorn`).
2. The ASGI server launches an **event loop** (usually using `asyncio`).
3. Incoming HTTP requests trigger coroutine-based route handlers.
4. Each request handler can `await`:
    - I/O (e.g. database queries, HTTP calls)
    - async libraries (e.g. `httpx`, `sqlalchemy.ext.asyncio`)
    - background tasks

This allows concurrency without blocking threads.