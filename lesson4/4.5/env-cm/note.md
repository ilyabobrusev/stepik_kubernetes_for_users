```bash
kubectl apply -f cm-env.yaml 
kubectl apply -f deployment-env.yaml
kubectl -n demo-cm logs deployment-with-env-54b89f5b64-x85dd
```