FROM golang:1.21 AS builder

WORKDIR /app

RUN printf 'package main\nimport "fmt"\nfunc main() {\nfmt.Println("Hello, Tetiana!")\n}' > main.go

RUN go build -o /app/myapp main.go

FROM alpine:3.14

WORKDIR /app

COPY --from=builder /app/myapp .

CMD ["./myapp"]
