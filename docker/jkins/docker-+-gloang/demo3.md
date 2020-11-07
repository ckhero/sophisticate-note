# Demo3

> FROM golang:1.15.2 AS buildImage
>
>     #some env
>     ENV PROJECT_NAME=rebate.o
>     #work file
>     WORKDIR /go/src/
>     COPY . .
>     # go env && git env
>     ENV GO111MODULE=on GOPROXY=https://goproxy.io,direct GOPRIVATE=*.zk020.cn PATH=$PATH:$GOROOT/bin:$GOPATH/bin GOINSECURE=git.zk020.cn GIT_TERMINAL_PROMPT=1
>     RUN echo http://18801613198%40163.com:suanni123@git.zk020.cn > git-credentials.txt && mv git-credentials.txt ~/.git-credentials
>     RUN git config --global credential.helper 'store --file ~/.git-credentials'
>     RUN go mod tidy
>     #build golang project
>     CMD CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build  -v -ldflags="-X main.VERSION=1.0.0 -X 'main.BUILD_TIME=`date`' -X 'main.GO_VERSION=`go version`'" -o ./$PROJECT_NAME ./cmd/main.go
>
>     #FROM alpine:latest
>     ##安装bin bash
>     #RUN apk update && apk add bash
>     #
>     #ENV PROJECT_NAME=rebate.o PORT=8014 WORKDIR=/app ORIGIN_CPATH=/go/src/builds/outputdir/config/
>     #
>     #WORKDIR $WORKDIR
>     #
>     #COPY --from=buildImage /go/src/$PROJECT_NAME .
>     #RUN chmod +x $PROJECT_NAME
>     #COPY --from=buildImage $ORIGIN_CPATH ./config/
>     #
>     #EXPOSE $PORT
>     #
>     #CMD $WORKDIR/$PROJECT_NAME --serviceId=0 --config=$WORKDIR/config/dev.yaml



