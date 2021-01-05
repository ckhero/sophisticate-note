## Demo1

> # go env
>
>     go version
>     export GOROOT=/var/jenkins_home/go
>     export GOPATH=/var/jenkins_home/go-project
>     export GOBIN=/var/jenkins_home/go-project-bin
>     export GO111MODULE=on
>     export GOPROXY=https://goproxy.io,direct
>     export GOPRIVATE=*.zk020.cn
>     export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
>     export GOINSECURE=git.zk020.cn
>     export GIT_TERMINAL_PROMPT=1
>     #build in linux
>     export GOOS=linux
>     export GOARCH=amd64 
>     echo "GOROOT: ${GOROOT}"
>     git config --global user.name ""
>     git config --global user.password ""
>     cd ${GOPATH}/rebate/
>     pwd
>     CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build  -v -ldflags="-X main.VERSION=1.0.0 -X 'main.BUILD_TIME=`date`' -X 'main.GO_VERSION=`go version`'" -o ${GOPATH}/rebate/rebate.o ${GOPATH}/rebate/cmd/main.go



