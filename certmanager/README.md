# cert-manager & Let's Encrypt

To deploy onto a k3s cluster:

```
export EMAIL=myemail@example.com
cat letsencrypt-prod.yaml | envsubst | kubectl apply -f -

cat traefik-https-redirect-middleware.yaml | envsubst | kubectl apply -f -
```

To see an example of an Ingress secured with Let's Encrypt certificate, see the plausible folder.

