FROM golang:1.22

WORKDIR /app


COPY main.go .


RUN go mod init service1 && go mod tidy


RUN go build -o service1 .

CMD ["./service1"]

