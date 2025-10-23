`asyncio` is Python’s framework for **asynchronous I/O**, built on an **event loop** that schedules and runs **coroutines** concurrently in a single thread. It provides **concurrency without parallelism**.

`asyncio` replaces traditional blocking I/O with **non-blocking**, cooperative multitasking.  
Each coroutine voluntarily **yields control** with `await`, allowing other tasks to run while waiting (e.g., for network responses or file reads).

| Component      | Description                                                       |
| -------------- | ----------------------------------------------------------------- |
| **Event Loop** | Core scheduler. Runs and manages tasks.                           |
| **Coroutine**  | Function defined with `async def`. Can be paused with `await`.    |
| **Task**       | Wrapper for a coroutine that runs on the event loop.              |
| **Future**     | Low-level object representing a result that is not yet available. |
| **await**      | Keyword to yield execution until awaited operation completes.     |

#### Execution Model

1. **Single thread** and **single process**.
2. Coroutines run cooperatively; each must yield explicitly.
3. No GIL contention because only one coroutine executes Python code at a time.
4. Suitable for high concurrency, not parallel computation.


| Scenario                            | Use `asyncio`?           |
| ----------------------------------- | ------------------------ |
| Many network requests               | ✅                        |
| Web servers (e.g. FastAPI, aiohttp) | ✅                        |
| File I/O                            | ✅ (with async libraries) |
| CPU-bound computation               | ❌ (use multiprocessing)  |

## References

- Python asyncio documentation
- Real Python: Async IO in Python
- PEP 3156 – Asynchronous I/O Support
- aiohttp – Async HTTP Client/Server