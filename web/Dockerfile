FROM golang:alpine AS builder
WORKDIR /src
COPY dispatcher.go .
RUN go build dispatcher.go
 
FROM alpine
WORKDIR /app
COPY --from=builder /src/dispatcher .
COPY static static
CMD ./dispatcher
 