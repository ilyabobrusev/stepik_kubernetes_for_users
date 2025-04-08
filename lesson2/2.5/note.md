```bash
kubectl apply -f ns.yaml
kubectl apply -f deployment.yaml
kubectl -n web-app-stage get pods
watch -n 1 kubectl -n web-app-stage get pods
kubectl -n web-app-stage delete pods goapp-deployment-xyz...
```

```bash
kubectl explain deployment.spec
kubectl explain deployment.spec.template
kubectl explain replicaset.spec.template
kubectl explain pod.spec
```

```bash
kubectl -n rolling get deployment
kubectl get ns
kubectl -n rolling get deployment
kubectl -n rolling get replicaset
kubectl -n rolling get pod
kubectl -n rolling get serviceaccount
kubectl get clusterrolebindings
kubectl -n rolling describe deployment
kubectl -n rolling scale deployment goapp-deployment --replicas 5

kubectl delete -f deployment.yaml
kubectl delete deployment -n rolling goapp-deployment
```