```bash
kubectl apply -f pod.yaml

kubectl exec -it curl-pod -- sh
curl http://goweb-svc.demo-clusterip/practice
curl http://goweb-svc.demo-clusterip.svc/practice
curl http://goweb-svc.demo-clusterip.svc.cluster.local/practice

kubectl -n demo-clusterip exec -it curl-pod -- sh
curl http://goweb-svc/practice
```
