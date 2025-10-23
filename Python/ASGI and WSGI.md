ASGI and WSGI are **Python web application interfaces** defining how servers communicate with frameworks.

- **WSGI (Web Server Gateway Interface):** Standard for **synchronous** apps.
- **ASGI (Asynchronous Server Gateway Interface):** Standard for **asynchronous** and **synchronous** apps.

|Aspect|**WSGI**|**ASGI**|
|---|---|---|
|Model|Synchronous|Asynchronous|
|Concurrency|One request per thread or process|Many requests per event loop|
|Protocols|HTTP only|HTTP, WebSocket, lifespan|
|Interface type|Callable function|Async callable coroutine|
|Threading|Blocks per request|Non-blocking I/O|
|Parallelism|via threads/processes|via async coroutines|


|Category|WSGI|ASGI|
|---|---|---|
|**Frameworks**|Flask, Django (classic)|FastAPI, Starlette, Django Channels|
|**Use case**|Simple web pages, blocking I/O|APIs, WebSockets, async I/O|
|**Performance**|Limited by threads|Scales efficiently with async I/O|
|**Scalability**|Heavy under high concurrency|Lightweight and scalable|
|**WebSocket support**|None|Native|
|**Backward compatibility**|Long-established|Modern replacement|