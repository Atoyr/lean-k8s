FROM golang:1.24 AS builder
WORKDIR /app
COPY . . 
ENV GCO_ENABLED=0
RUN go build -o hello-server .

FROM scratch
COPY --from=builder /app/hello-server /hello-server
ENTRYPOINT ["/hello-server"]
