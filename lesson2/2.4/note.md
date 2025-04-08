```bash
kubectl apply -f ns.yaml
kubectl get ns
kubectl delete -f ns.yaml --wait=false

kubectl create ns examples-dev2
kubectl get ns
kubectl delete ns examples-dev2

kubectl apply -f web-app-ns.yaml
kubectl apply -f pod.yaml
kubectl -n web-app-dev get pods -o wide
kubectl -n web-app-dev describe pods simple-web
kubectl -n web-app-dev port-forward pod/simple-web 8080:8080
kubectl -n web-app-dev get pods simple-web -o yaml
kubectl get pods -n web-app-dev simple-web -o yaml > 1.yaml
kubectl get pods -n web-app-dev simple-web -o yaml | yq .spec.containers[]
kubectl -n web-app-dev get pods --show-labels
kubectl describe pod -n web-app-dev simple-web
kubectl -n web-app-dev logs -f simple-web
kubectl exec -it -n web-app-dev pod/simple-web -c web -- sh
minikube addons enable metrics-server
kubectl top pods -n web-app-dev
kubectl delete pod -n web-app-dev simple-web
```

```text
kind                  ## вид ресурса, мы уже знаем 2 вида ресурсов k8s: Namespace, Pod
metadata.name         ## имя Пода, в данном случае это simple-web.
metadata.labels       ## ярлыки (или метки) для пода, в этом случае ярлык app=goweb можно использовать для поиска или группировки подов.
spec.containers.name  ## имя контейнера внутри пода. В поде может быть несколько контейнеров, здесь контейнер называется web.
spec.containers.image ## образ контейнера, который будет использоваться. Замените значение на свой образ, созданный в предыдущих уроках.
spec.containers.ports ## указывает порт 8080, который будет открыт для доступа извне.

## image: <имя_пользователя>/<репозиторий>/<тег>
```
