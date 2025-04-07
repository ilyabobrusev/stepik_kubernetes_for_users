# Создаем временный Докер Образ и называем его builder
FROM golang:1.20 AS builder                                  
WORKDIR /app
COPY . .
# Компилируем приложение специально для дальнейшего запуска в Alpine
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o app . 


# Создаем финальный Докер Образ на базе легковесного alpine
FROM alpine:latest                       
WORKDIR /root/
# Копируем собранное приложение из образа builder
COPY --from=builder ./app .              
EXPOSE 8080
CMD ["./app"]

