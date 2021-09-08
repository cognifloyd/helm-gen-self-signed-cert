# `helm-gen-self-signed-cert` Helm Chart

A Helm chart that generates a self signed cert and saves it in a k8s Secret.

> Do not use this chart for publicly accessible services! If that's what you need
> try Let's Encrypt, cert-manager, or some other certificate generation service.

This is a companion chart to be used alongside other helm-charts. It uses helm/sprig functions to
generate a self-signed TLS/x.509 cert. It generates an ephemeral CA, and then generates a signed
cert using that CA. By default, the cert is good for 365 days, but you can configure that.

Only use this chart if the security trade-offs for self-signed certs are acceptable
in your (firewalled) k8s cluster. If not, consider using Let's Encrypt, cert-manager,
or some other service.
