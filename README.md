# EVE Notifications - API Gateway
This is a simple Caddyserver reverse proxy that routes external requests to
services within the cluster.

Caddyserver was chossen because of its simplicity in configuration and its
integration with Lets Encrypt which automatically creates SSL certs.

The API Gateway is exposed using a static IP from Google and the Kubernetes
service has an "externalIPs" spec. If this was a large scale deployment this
would have to be replaced with a proper load balancer. However since all of the
traffice can be handled by one container and is all running on one node anyways
this is cheaper than running a load balancer.