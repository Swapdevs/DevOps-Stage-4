# Use Go as base image
FROM golang:1.18-alpine as builder

# Set working directory
WORKDIR /app

# Copy go.mod and go.sum files
COPY go.mod go.sum ./

# Download dependencies
RUN go mod download

# Copy the source code
COPY . .

# Build the application
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o auth-api .

# Use a minimal alpine image for the final stage
FROM alpine:latest

# Set working directory
WORKDIR /root/

# Copy the binary from the builder stage
COPY --from=builder /app/auth-api .

# Expose port
EXPOSE 8081

# Command to run the executable
CMD ["./auth-api"]
