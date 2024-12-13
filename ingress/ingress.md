In Kubernetes, Ingress and Ingress Controller are components used to manage external access to services running in the cluster. They provide advanced routing capabilities beyond what basic service types like NodePort or LoadBalancer offer.
Ingress

An Ingress is an API object that manages external HTTP and HTTPS traffic to services within a Kubernetes cluster. It acts as a reverse proxy and allows you to:

    Expose multiple services through a single IP address or domain name.
    Perform advanced routing based on:
        Hostname (e.g., example.com, api.example.com)
        Path (e.g., /app1, /app2)
    Handle SSL/TLS termination for secure communication.
    Add custom rules or features like redirects.

Ingress Controller

An Ingress Controller is the actual implementation that processes the Ingress resources and handles the traffic routing. While an Ingress resource defines the rules, the Ingress Controller enforces them by:

    Configuring underlying components like proxies (e.g., Nginx, Traefik, HAProxy).
    Listening to Ingress API objects for updates and managing routing accordingly.

Popular Ingress Controllers

    NGINX Ingress Controller: A widely-used implementation that uses NGINX as the reverse proxy.
    Traefik: Lightweight and dynamic with built-in support for modern protocols.
    HAProxy: High-performance and suitable for complex routing.
    Cloud Provider Controllers: Managed offerings like AWS ALB Ingress Controller or GCP HTTP(S) Load Balancer.

Relationship Between Ingress and Ingress Controller

    Ingress: Defines what traffic should do.
    Ingress Controller: Implements how the traffic rules are enforced.

Without an Ingress Controller running in your cluster, the Ingress resource won’t function.
Why Use Ingress?

    Centralized Routing: Manage access to multiple services with a single entry point.
    TLS/SSL Termination: Offload HTTPS handling to the Ingress Controller.
    Dynamic Scaling: Works well with auto-scaling services.
    Cost-Effective: Reduces the need for multiple external load balancers (e.g., in a cloud environment).