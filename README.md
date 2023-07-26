# gitops-deployment-manifests

```shell
$ argocd app create static-website-by-nginx \
  --repo https://github.com/Josaber/gitops-deployment-manifests.git \
  --path static-website-by-nginx \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace default \
  --sync-policy automated \
  --values values.yaml \
  --values values-test.yaml \
  --values values-image-test.yaml

$ kubectl port-forward svc/static-website-by-nginx 9090:80
$ argocd app sync static-website-by-nginx
$ argocd app delete static-website-by-nginx
```
