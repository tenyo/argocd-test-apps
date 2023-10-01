# external-dns

## Secret

The chart expects a secret `cloudflare-api-secret` with the Cloudflare API token.

```
kubectl -n external-dns create secret generic cloudflare-api-secret --from-literal=cloudflare_api_token=CHANGEME
```