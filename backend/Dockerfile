FROM gitlab.praktikum-services.ru:5050/k.kudelich/momo-store/golang:1.20.0-alpine as builder
WORKDIR /build
COPY go.mod .
RUN go mod download
COPY . .
RUN go build -o /main ./cmd/api

FROM gitlab.praktikum-services.ru:5050/k.kudelich/momo-store/alpine:3.17.1
COPY --from=builder main /bin/main
ENTRYPOINT ["/bin/main"]
