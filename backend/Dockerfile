FROM golang:1.20.1-buster as build
# デフォルトディレクトリが /go なので GOPATH だと勘違いされて go mod できないので app にする
WORKDIR /app
COPY . .
RUN go build -o main ./cmd/main

FROM golang:1.20.1-buster as prod
WORKDIR /app
COPY --from=build /app/main main
ENTRYPOINT ["./main"]