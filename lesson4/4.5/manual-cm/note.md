```bash
openssl genrsa -out server.key 2048
kubectl -n demo-cm create configmap test-tls-key --from-file="server.key"
kubectl -n demo-cm create configmap test-tls-key --from-file="server.key" --dry-run="client" -o yaml
kubectl apply -f key_cm.yaml
kubectl -n demo-cm get cm
kubectl -n demo-cm describe cm test-tls-key
```
