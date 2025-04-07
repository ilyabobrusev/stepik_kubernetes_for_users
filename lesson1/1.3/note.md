```bash
docker build . -t go:v0.2
docker run -p 8080:8080 go:v0.2
```

```Dockerfile
RUN apt-get update && apt-get install -y ca-certificates && update-ca-certificates && rm -rf /var/lib/apt/lists/*
```

```Dockerfile
FROM python:3.9
COPY requirements.txt /app/
RUN pip install -r /app/requirements.txt
COPY . /app
```

# https://docs.docker.com/build/building/best-practices/

