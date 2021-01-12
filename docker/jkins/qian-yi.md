## 迁移

> [https://blog.csdn.net/kouryoushine/article/details/100075629](https://blog.csdn.net/kouryoushine/article/details/100075629)

## 步骤

> 1. stopservice
>
> 2. copy文件  
>    1. tar -cvf jenkins.tar /var/lib/jenkins/
>
>    1. scp jenkins.tar root@xx.xx.xx.xx:/xx/xx/jenkins
>
>    2. tar -xvf jenkins.tar
>
> 3. 安装git
>
> 4. 把jenkis加入docker用户组
>
>    1. sudo gpasswd -a jenkins docker
>
> 5. 重启



