```bash
kubectl -n demo-nodeport get svc
kubectl get nodes -o wide
minikube service --url -n demo-nodeport goweb-svc-nodeport
# http://192.168.49.2:30050
docker run -it --network minikube curlimages/curl http://192.168.49.2:30050/stepik
```
