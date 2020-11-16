# Pipeline

## Demo1

> ```
> pipeline {
>   agent any
>   stages {
>       stage('Pull') {
>       steps {
>           git branch: 'features-docker', url: 'http://18801613198%40163.com:suanni123@git.zk020.cn/youmi-wx-apps/rebate.git'
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

## Demo2

> ```
> pipeline {
>   agent any
>   environment {
>         BUILD_TAG = 'vr'
>     }
>   stages {
>   /*    stage('Pull') {
>       steps {
>           git branch: 'features-docker', url: 'http://18801613198%40163.com:suanni123@git.zk020.cn/youmi-wx-apps/rebate.git'
>       }
>     }
>
>     stage('Build') {
>       steps {
>         sh 'docker build -t rebate:${BUILD_TAG} .'
>       }
>     }
>
>         stage('Yaml') {
>       steps {
>         sh "sed -i.bak 's/TAG/${env.BUILD_TAG}/' Deployment.yaml"
>       }
>     }*/
>     stage('Deploy2') {
>       steps {
>         withKubeConfig([credentialsId: "af31a910-9490-4e2d-bbe0-674bbe57e8ad",serverUrl:"https://192.168.65.3:6443"]) {
>             sh "/usr/local/bin/kubectl get nodes"
>         }
>       }
>     }
>   }
> }
> ```



