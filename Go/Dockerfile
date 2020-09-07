FROM golang:1.15.1-alpine3.12 as builder

WORKDIR /go/src/app

COPY . .

RUN CGO_ENABLED=0 GOOS=linux go build -ldflags="-s -w"

FROM scratch

WORKDIR /go/src/app

COPY --from=builder /go/src/app/app .

CMD ["./app"]