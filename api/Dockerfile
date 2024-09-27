# stage 1 : Build the application
FROM golang:alpine as builder

WORKDIR /build

COPY go.mod go.sum ./

RUN go mod download

COPY . .

RUN go build -o main.

EXPOSE 3000

CMD ["./main"]

# # stage 2 : Create the final image
# FROM alpine:latest

# RUN apk --no-cache add ca-certificates

# WORKDIR /root/

# COPY --from=builder /build/main .

# EXPOSE 3000

# CMD ["./main"]