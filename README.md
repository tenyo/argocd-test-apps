# argocd-test-apps

## Initial ArgoCD bootstrap

Install barebone argo-cd
```
helm repo add argo https://argoproj.github.io/argo-helm
helm install argocd argo/argo-cd -n argocd --create-namespace
```

Get admin password
```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

Port forward
```
kubectl port-forward service/argocd-server -n argocd 8080:443
```

Login at https://localhost:8080/ and create the app-of-apps, or you can create it from the manifest in this repo:
```
kubectl -n argocd apply -f app-of-apps.yaml
```

Sync the app-of-apps and then just sync the `metallb`` and `ingress-nginx` apps.
