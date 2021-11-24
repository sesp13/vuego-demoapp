FROM golang:1.16-alpine

WORKDIR /app

COPY go.mod ./
COPY go.sum ./
RUN go mod download

COPY *.go ./

RUN go build -o /go-server

EXPOSE 4001

ENV PORT=4001

CMD [ "/go-server" ]