**SSL termination** is the process in which a proxy server (often a reverse proxy) **decrypts incoming HTTPS traffic** before forwarding it to backend servers.

**Key points**

- The reverse proxy handles TLS/SSL decryption.
- Backend servers receive plain HTTP traffic.
- This reduces CPU load on backend servers.
- Centralizes certificate management at the proxy layer.

**Why it's used**

- Performance: backend servers avoid expensive cryptographic operations.
- Simplicity: certificates are maintained in one place.
- Security control: the proxy can inspect, filter, or route traffic after decryption.

**Flow**  
Client (HTTPS) → Reverse Proxy (decrypts) → Backend (HTTP)