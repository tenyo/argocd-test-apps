# argocd

Install
```
helm install argocd argocd/ -n argocd --create-namespace
```

Get admin password
```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

Port forward
```
kubectl -n argocd port-forward svc/argocd-server 8443:443
```

Login at https://localhost:8443/
