# ===== Stage 1: Build =====
FROM golang:1.20-alpine AS builder

WORKDIR /app

COPY . .

RUN go build -o app

# ===== Stage 2: Run =====
FROM alpine:latest

WORKDIR /app

COPY --from=builder /app/app .

EXPOSE 8080

CMD ["./app"]