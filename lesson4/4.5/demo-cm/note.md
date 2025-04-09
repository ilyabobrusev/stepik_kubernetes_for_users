```bash
kubectl apply -f ns.yaml
kubectl apply -f configmap.yaml
kubectl -n demo-cm get configmap
kubectl -n demo-cm get cm
kubectl -n demo-cm describe cm first-cm
kubectl -n demo-cm describe po pod-with-cm
kubectl -n demo-cm exec -it pod-with-cm -- sh
# cat /etc/config/config.yaml
kubectl -n demo-cm logs pod-with-cm
```
```bash
kubectl apply -f deployment.yaml
kubectl -n demo-cm get deployment
kubectl -n demo-cm describe deployment deployment-with-cm
kubectl -n demo-cm get pod
kubectl -n demo-cm exec -it pod/deployment-with-cm-569997bc8b-5q9g5 -- cat /etc/config/config.yaml
```
