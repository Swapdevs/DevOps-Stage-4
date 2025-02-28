# Dockerfile for Auth API
FROM golang:1.23
WORKDIR /app
COPY . .
RUN go build -o auth-api .
EXPOSE 8080
CMD ["./auth-api"]