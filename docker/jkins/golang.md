## Demo1

> go version  
>     export GOROOT=/var/jenkins\_home/go  
>     export GOPATH=/var/jenkins\_home/go-project  
>     export GO111MODULE=on  
>     export GOPROXY=[https://goproxy.io,direct](https://goproxy.io,direct)  
>     export GOPRIVATE=\*.zk020.cn  
>     export PATH=$PATH:$GOROOT/bin:$GOPATH/bin  
>     export GOINSECURE=git.zk020.cn  
>     export GIT\_TERMINAL\_PROMPT=1  
>     go env   
>     echo "GOROOT: ${GOROOT}"  
>     git config --global user.name "188801613198@163.com"  
>     git config --global user.password "suanni123"  
>     git config --global credential.helper store  
>     cd /var/jenkins\_home/go-project/rebate/  
>     pwd  
>     go mod tidy  
>     go build  -v -ldflags="-X main.VERSION=1.0.0 -X 'main.BUILD\_TIME=`date`' -X 'main.GO\_VERSION=`go version`'" -o /var/jenkins\_home/go-project-bin/rebate.o /var/jenkins\_home/go-project/rebate/cmd/main.go



