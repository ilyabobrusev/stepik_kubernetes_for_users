#### https://minikube.sigs.k8s.io/docs/start/?arch=%2Fwindows%2Fx86-64%2Fstable%2F.exe+download


```bash
minikube start
minikube status
kubectl --help

kubectl create deployment first-deployment  --image=ilyabobrusev/lesson1:v0.2

kubectl apply -f deployment.yaml
kubectl get deployments
kubectl get pod

kubectl get po -A
minikube kubectl -- get po -A
alias kubectl="minikube kubectl --"
minikube dashboard

minikube pause
minikube unpause
minikube stop
minikube config set memory 9001
minikube addons list
minikube start -p aged --kubernetes-version=v1.16.1
minikube delete --all
```