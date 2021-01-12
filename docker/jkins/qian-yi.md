## 迁移

> [https://blog.csdn.net/kouryoushine/article/details/100075629](https://blog.csdn.net/kouryoushine/article/details/100075629)

## 步骤

> 1. cop文件  
>    1. tar -cvf jenkins.tar /var/lib/jenkins/
>
>    1. scp jenkins.tar root@xx.xx.xx.xx:/xx/xx/jenkins
>
>    2. tar -xvf jenkins.tar
>
> 2. 安装git
>
> 3. 把jenkis加入docker用户组
>
>    1. sudo gpasswd -a jenkins docker



