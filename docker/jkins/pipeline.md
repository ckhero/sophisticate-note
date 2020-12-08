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

demo3

> ```
> pipeline {
>   agent any
>   environment {
>     BUILD_TAG = 'vr'
>     PROJECT_NAME = 'rebate'
>   }
>   stages {
>     stage('Pull') {
>       steps {
>          
>         git branch: 'features-docker', url: 'http://18801613198%40163.com:suanni123@git.zk020.cn/youmi-wx-apps/rebate.git'
>         script {
>             env.BUILD_TAG = '$(git rev-parse --short HEAD) '
>         }
>       }
>     }
>
>     stage('Build') {
>       steps {
>         sh '/usr/local/bin/docker build -t rebate:${env.BUILD_TAG} .'
>       }
>     }
>
>     stage('Yaml') {
>       steps {
>         sh "sed -i.bak 's/TAG/${env.BUILD_TAG}/' Deployment.yaml"
>       }
>     }
>     stage('Deploy2') {
>       steps {
>         sh "/usr/local/bin/kubectl apply -f Deployment.yaml"
>       }
>     }
>   }
> }
> ```

demo4

> ```
> node {
>     stage('PULL') {
>         git branch: 'master', url: 'http://18801613198%40163.com:suanni123@git.zk020.cn/youmi-micro/youmi-micro-cluster.git'
>         env.ENV = 'test'
>         env.VERSION = '$(git rev-parse --short HEAD).toString()'
>         env.BUILD_TAG = 'registry.cn-shanghai.aliyuncs.com/youmi-go/youmi-micro-cluster:coupon-${ENV}-v${BUILD_NUMBER}'
>     }
>     stage('BUILD') {
>         sh(returnStdout: true, script: "docker login --username=中快文化传媒 registry.cn-shanghai.aliyuncs.com -pZku123456")
>         docker.build("${BUILD_TAG}", "-f ./src/youmi_micro_coupon/Dockerfile .").push()
>     }
>     stage('DEPLOY') {
>         withCredentials([kubeconfigFile(credentialsId: 'aliyun-k8s',variable: 'KUBECONFIG')]) {
>           sh(returnStdout: true, script: "sed -i 's/\${ENV}/${ENV}/' ./src/youmi_micro_coupon/coupon.yaml")
>           sh(returnStdout: true, script: "sed -i 's/\${VERSION}/${BUILD_NUMBER}/' ./src/youmi_micro_coupon/coupon.yaml")
>           sh 'kubectl apply -f  ./src/youmi_micro_coupon/coupon.yaml'
>         }
>     }
> }
> ```

demo5

> node {
>         stage('PULL') {
>             git branch: 'master', url: 'http://18801613198%40163.com:suanni123@git.zk020.cn/youmi-micro/youmi-micro-cluster.git'
>             env.ENV = 'test'
>             env.VERSION = '$(git rev-parse --short HEAD).toString()'
>             env.BUILD_TAG = 'registry.cn-shanghai.aliyuncs.com/youmi-go/youmi-micro-cluster:coupon-${ENV}-v${BUILD_NUMBER}'
>             env.PROJECT_NAME = "coupon"
>             env.PROJECT_FILE = "youmi_micro_coupon"
>             env.PORT = "5063"
>             env.NODE_PORT = "31063"
>         }
>         stage('BUILD') {
>             sh "sed -i 's/\${ENV}/${ENV}/' ./deploy/Dockerfile"
>             sh "sed -i 's/\${PROJECT_NAME}/${PROJECT_NAME}/' ./deploy/Dockerfile"
>             sh "sed -i 's/\${PROJECT_FILE}/${PROJECT_FILE}/' ./deploy/Dockerfile"
>             sh "sed -i 's/\${PORT}/${PORT}/' ./deploy/Dockerfile"
>             sh(returnStdout: true, script: "docker login --username=中快文化传媒 registry.cn-shanghai.aliyuncs.com -pZku123456")
>             docker.build("${BUILD_TAG}", "-f ./deploy/Dockerfile .").push()
>         }
>         stage('DEPLOY') {
>             withCredentials([kubeconfigFile(credentialsId: 'aliyun-k8s',variable: 'KUBECONFIG')]) {
>               sh(returnStdout: true, script: "sed -i 's/\${ENV}/${ENV}/' ./deploy/Deployment.yaml")
>               sh(returnStdout: true, script: "sed -i 's/\${PROJECT_NAME}/${PROJECT_NAME}/' ./deploy/Deployment.yaml")
>               sh(returnStdout: true, script: "sed -i 's/\${PORT}/${PORT}/' ./deploy/Deployment.yaml")
>               sh(returnStdout: true, script: "sed -i 's/\${NODE_PORT}/${NODE_PORT}/' ./deploy/Deployment.yaml")
>               sh(returnStdout: true, script: "sed -i 's/\${VERSION}/${BUILD_NUMBER}/' ./deploy/Deployment.yaml")
>               sh 'kubectl apply -f  ./deploy/Deployment.yaml'
>             }
>             sh 'docker rmi -f `docker image ls -f dangling=true -q`'
>         }
>     }



