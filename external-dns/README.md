# external-dns

## Secret

The chart expects a secret `cloudflare-apikey` for the Cloudflare API key.

```
kubectl -n external-dns create secret generic cloudflare-apikey --from-literal=cloudflare_api_token=CHANGEME
```