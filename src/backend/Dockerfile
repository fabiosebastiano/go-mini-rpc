FROM golang:1.15

ENV HOME /root
ENV PATH $PATH:/usr/local/go/bin
ENV GOPATH /go 
RUN echo $GOPATH
RUN go get -u github.com/golang/protobuf/protoc-gen-go
RUN go get -u github.com/grpc-ecosystem/go-grpc-middleware/logging/zap
RUN go get -u go.uber.org/zap

# Make sure to push your protos to your github account
RUN go get -u github.com/fabiosebastiano/go-mini-rpc/proto/gen

WORKDIR /go/src/micro-sample-backend
COPY . .

RUN go build -o /usr/local/bin/micro-sample-backend

CMD ["micro-sample-backend"]