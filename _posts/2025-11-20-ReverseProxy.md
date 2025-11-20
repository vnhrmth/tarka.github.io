# Reverse Proxy

## What is a Reverse Proxy?

A **reverse proxy** is a mediator server that handles client requests on behalf of backend servers. If the backend server needs to be hidden from the client, the reverse proxy acts as an intermediary. The client sends requests to the reverse proxy, which forwards them to the backend server without the client noticing.

## Why is it Used?

- **Privacy**: The reverse proxy hides the IP address and identity of the backend server.
- **Security**: In case of a breach, the backend server remains protected since clients never interact with it directly.
- **Load Balancing**: Distributes incoming traffic across multiple backend servers to prevent overload and ensure efficient resource usage.
- **Caching**: Frequently accessed URLs can be cached at the proxy level, reducing load on backend servers and improving response times.
