# cert-manager

## Secret

The chart expects a secret `cloudflare-api-secret` with the Cloudflare API token.

```
kubectl -n cert-manager create secret generic cloudflare-api-secret --from-literal=api-token=CHANGEME
```