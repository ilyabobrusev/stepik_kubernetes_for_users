### Манифест Деплоймента с заданнымиrequests и limits
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: goapp-deployment
  namespace: demo-ingress
  labels:
    app: goapp
spec:
  replicas: 1
  selector:
    matchLabels:
      app: goapp
  template:
    metadata:
      labels:
        app: goapp
    spec:
      containers:
      - name: web
        image: ksxack/lesson1:v0.2
        ports:
        - containerPort: 8080
        resources:
          requests:
            memory: "100Mi"
            cpu: "200m"
          limits:
            memory: "150Mi"
            cpu: "300m"
```

### livenessProbe, readinessProbe, startupProbe
```yaml
apiVersion: v1
kind: Pod
metadata:
  labels:
    test: my-pod
  name: my-pod-http
spec:
  containers:
  - name: containername
    image: k8s.gcr.io/liveness
    args:
    - /server
    livenessProbe:
      httpGet:
        path: /healthz
        port: 8080
      initialDelaySeconds: 3
      periodSeconds: 2
    readinessProbe:
      exec:
        command:
          - cat
          - /tmp/healthy
      initialDelaySeconds: 5
      periodSeconds: 5
    startupProbe:
      httpGet:
        path: /healthz
        port: liveness-port
      failureThreshold: 30
      periodSeconds: 10
```
