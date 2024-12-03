# backend/Dockerfile
FROM golang:1.19
WORKDIR /app
COPY . .
RUN go build -o app main.go
EXPOSE 8080
CMD ["./app"]
