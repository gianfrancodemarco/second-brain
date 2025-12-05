An API gateway is an [API management](https://www.redhat.com/en/topics/api/what-is-api-management) tool that sits between a client and a collection of backend services. In this case, a client is the application on a user’s device and the backend services are those on an enterprise’s servers. 

An API gateway is a component of application delivery (the combination of services that serve an application to users) and acts as a [[Proxy and Reverse proxy|reverse proxy]] to accept all [application programming interface (API)](https://www.redhat.com/en/topics/api/what-are-application-programming-interfaces) calls, aggregate the various services required to fulfill them, and return the appropriate result. In simpler terms, an API gateway is a piece of software that intercepts API calls from a user and routes them to the appropriate backend service.

## Why use an API gateway?

Most enterprise APIs are deployed via API gateways. It’s usual for API gateways to handle common tasks that are used across a system of API services, such as user authentication, [[Rate Limiting]], and statistics.

At its most basic, an API service accepts a remote request and returns a response. But real life is never that simple. Consider your various concerns when you host large-scale APIs.

- You want to protect your APIs from overuse and abuse, so you use an authentication service and [[Rate Limiting]]. 
- You want to understand how people use your APIs, so you’ve added analytics and monitoring tools.
- If you have [monetized APIs](https://www.redhat.com/en/topics/api/what-is-api-monetization), you’ll want to connect to a billing system.
- You may have adopted a [microservices](https://www.redhat.com/en/topics/microservices/what-are-microservices) architecture, in which case a single request could require calls to dozens of distinct applications.
- Over time you’ll add some new API services and retire others, but your clients will still want to find all your services in the same place.

Your challenge is offering your clients a simple and dependable experience in the face of all this complexity. An API gateway is a way to decouple the client interface from your backend implementation. When a client makes a request, the API gateway breaks it into multiple requests, routes them to the right places, produces a response, and keeps track of everything.

### Traffic management

API gateways throttle and manage traffic through various mechanisms designed to control the rate and volume of incoming requests and ensure optimal performance and resource utilization.

- **[[Rate Limiting]]** policies specify the maximum number of requests allowed within a certain time period (e.g., requests per second, minute, hour) for each client or API key, protecting backend services from overload.
- **Request throttling** policies define rules and limits for regulating request traffic, such as maximum request rates, burst allowances, and quotas.
- **Concurrency control policies** specify the maximum number of concurrent connections or requests that can be handled simultaneously by the backend servers.
- **Circuit breaking policies** monitor the health and responsiveness of backend servers and temporarily block or redirect traffic away from failing or slow services to prevent cascading failures and maintain overall system stability.
- **Dynamic load balancing** from API gateways continuously monitors server health and adjusts traffic routing in real-time to handle spikes in demand, minimize response times, and maximize throughput.

## Authentication && Authorization with API gateways

## References

https://www.redhat.com/en/topics/api/what-does-an-api-gateway-do