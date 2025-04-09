```bash
kubectl apply -f demo-clusterIP/
kubectl -n demo-clusterip get deployment
kubectl -n demo-clusterip get pods
kubectl -n demo-clusterip get service
watch kubectl -n demo-clusterip get svc
watch kubectl -n demo-clusterip get po -o wide
kubectl -n demo-clusterip describe svc goweb-svc
kubectl -n demo-clusterip port-forward svc/goweb-svc 8181:80
```