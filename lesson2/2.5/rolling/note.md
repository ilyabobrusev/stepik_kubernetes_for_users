```bash
Проверка истории деплоймента:
kubectl -n rolling rollout history deployment/goapp-deployment

Откат к предыдущей версии:
kubectl -n rolling rollout undo deployment/goapp-deployment


Плавный рестарт Подов:
kubectl -n rolling rollout restart deployment/goapp-deployment
```

```bash
kubectl delete -f rolling.yaml --wait=false
kubectl delete deployment -n rolling goapp-deployment
```
