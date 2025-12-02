A **proxy** and a **reverse proxy** are both intermediary servers, but they sit on opposite sides of a network flow and serve different purposes.

## Proxy (Forward Proxy)

A **proxy** sits **between a client and the internet**.  
Clients send their requests to the proxy, which forwards them to the destination server.

**Main purposes**

- Privacy: hides the client’s IP address
- Access control: enforces corporate network rules
- Caching: speeds up repeated requests
- Filtering: blocks unwanted sites or content

**Flow**  
Client → Proxy → Server → Proxy → Client

**Example use case**  
Employees in a company must browse the web through a proxy to filter traffic and log activity.

## Reverse Proxy

A **reverse proxy** sits **in front of one or more servers** and receives requests on their behalf.

**Main purposes**

- Load balancing: distributes traffic across multiple servers
- Security: hides internal servers from the public internet
- Caching: reduces load on backend servers
- [[SSL termination]]: offloads HTTPS encryption work

**Flow**  
Client → Reverse Proxy → Backend Server(s) → Reverse Proxy → Client

**Example use case**  
A large website uses Nginx as a reverse proxy to balance requests across multiple application servers.