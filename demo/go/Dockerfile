FROM golang

WORKDIR /app

COPY . .

RUN go get -v && \
      CGO_ENABLED=0 GOOS=linux go build -o dwx

RUN ./dwx

