FROM golang AS builder

WORKDIR /app

COPY . .


RUN go get -v && \
      CGO_ENABLED=0 GOOS=linux go build -o dwx

FROM scratch

COPY --from=builder /app/dwx .

RUN ./app

