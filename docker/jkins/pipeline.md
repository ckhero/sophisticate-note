# Pipeline

## Demo1

> ```
> pipeline {
>   agent any
>   stages {
>   	stage('Pull') {
>       steps {
>       	git branch: 'features-docker', url: 'http://18801613198%40163.com:suanni123@git.zk020.cn/youmi-wx-apps/rebate.git'
>       }
>     }
>
>     stage('Build') {
>       steps {
>         sh 'docker build -t rebate:pipeline .'
>       }
>     }
>
>     stage('Deploy2') {
>       steps {
>         sh 'docker run -d --name rebate_pipeline -p 8014:8014 rebate:pipeline'
>       }
>     }
>
>   }
> }
> ```



