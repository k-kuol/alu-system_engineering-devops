## Load Balancer

This project introduces redundancy to the web infrastructure by adding a second
web server and placing both behind a load balancer. It covers custom HTTP
response headers, HAProxy installation and configuration, and round-robin
traffic distribution.

### Directory: `load_balancer`

| File | Description |
| --- | --- |
| [0-custom_http_response_header](load_balancer/0-custom_http_response_header) | Configures nginx to add a custom `X-Served-By` header containing the server's hostname. |
| [1-install_load_balancer](load_balancer/1-install_load_balancer) | Installs and configures HAProxy to distribute traffic between web-01 and web-02 using round-robin. |
