# Pipeline

## Demo1

> ```
> pipeline {
>   agent any
>   stages {
>       stage('Pull') {
>       steps {
>           git branch: 'features-docker', url: 'http://183198%40163.com:mima@git.test.cn/test.git'
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
>           git branch: 'features-docker', url: 'http://18613198%40163.com:mima@git.test.cn/test.git'
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
>         git branch: 'features-docker', url: 'http://18801613198%40163.com:mima@git.test.cn/test.git'
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
>         git branch: 'master', url: 'http://188%40163.com:mima@git.test.cn/test.git'
>         env.ENV = 'test'
>         env.VERSION = '$(git rev-parse --short HEAD).toString()'
>         env.BUILD_TAG = 'TAG'
>     }
>     stage('BUILD') {
>         sh(returnStdout: true, script: "docker login --username=username registry.cn-shanghai.aliyuncs.com -pmima")
>         docker.build("${BUILD_TAG}", "-f ./src/youmi_micro_coupon/Dockerfile .").push()
>     }
>     stage('DEPLOY') {
>         withCredentials([kubeconfigFile(credentialsId: 'aliyun-k8s',variable: 'KUBECONFIG')]) {
>           sh(returnStdout: true, script: "sed -i 's/\${ENV}/${ENV}/' ./src//coupon.yaml")
>           sh(returnStdout: true, script: "sed -i 's/\${VERSION}/${BUILD_NUMBER}/' ./src//coupon.yaml")
>           sh 'kubectl apply -f  ./src//coupon.yaml'
>         }
>     }
> }
> ```

demo5

node {  
        stage\('PULL'\) {  
            git branch: 'master', url: ''  
            env.ENV = 'test'  
            env.VERSION = '$\(git rev-parse --short HEAD\).toString\(\)'  
            env.BUILD\_TAG = ':coupon-${ENV}-v${BUILD\_NUMBER}'  
            env.PROJECT\_NAME = "coupon"  
            env.PROJECT\_FILE = ""  
            env.PORT = "5063"  
            env.NODE\_PORT = "31063"  
        }  
        stage\('BUILD'\) {  
            sh "sed -i 's/${ENV}/${ENV}/' ./deploy/Dockerfile"  
            sh "sed -i 's/${PROJECT\_NAME}/${PROJECT\_NAME}/' ./deploy/Dockerfile"  
            sh "sed -i 's/${PROJECT\_FILE}/${PROJECT\_FILE}/' ./deploy/Dockerfile"  
            sh "sed -i 's/${PORT}/${PORT}/' ./deploy/Dockerfile"  
            sh\(returnStdout: true, script: "docker login --username=username registry.cn-shanghai.aliyuncs.com -pmima"\)  
            docker.build\("${BUILD\_TAG}", "-f ./deploy/Dockerfile ."\).push\(\)  
        }  
        stage\('DEPLOY'\) {  
            withCredentials\(\[kubeconfigFile\(credentialsId: 'aliyun-k8s',variable: 'KUBECONFIG'\)\]\) {  
              sh\(returnStdout: true, script: "sed -i 's/${ENV}/${ENV}/' ./deploy/Deployment.yaml"\)  
              sh\(returnStdout: true, script: "sed -i 's/${PROJECT\_NAME}/${PROJECT\_NAME}/' ./deploy/Deployment.yaml"\)  
              sh\(returnStdout: true, script: "sed -i 's/${PORT}/${PORT}/' ./deploy/Deployment.yaml"\)  
              sh\(returnStdout: true, script: "sed -i 's/${NODE\_PORT}/${NODE\_PORT}/' ./deploy/Deployment.yaml"\)  
              sh\(returnStdout: true, script: "sed -i 's/${VERSION}/${BUILD\_NUMBER}/' ./deploy/Deployment.yaml"\)  
              sh 'kubectl apply -f  ./deploy/Deployment.yaml'  
            }  
            sh 'docker rmi -f `docker image ls -f dangling=true -q`'  
        }  
    }

## Demo6

> node {
>
> ```
> stage\('PULL'\) {
>
>     checkout\(\[$class: 'GitSCM', 
>
>                       branches: \[\[name: "${params.BRANCH}"\]\], 
>
>                       doGenerateSubmoduleConfigurations: false, 
>
>                       extensions: \[\], 
>
>                       gitTool: 'Default', 
>
>                       submoduleCfg: \[\], 
>
>                       userRemoteConfigs: \[\[url: '',credentialsId: 'git'\]\]
>
>                     \]\)
>
>     env.ENV = 'test'
>
>     env.VERSION = '$\(git rev-parse --short HEAD\).toString\(\)'
>
>     env.BUILD\_TAG = ''
>
>     env.PROJECT\_NAME = "coupon"
>
>     env.PROJECT\_FILE = ""
>
>     env.PORT = "5063"
>
>     env.NODE\_PORT = "31063"
>
> }
>
> stage\('BUILD'\) {
>
>     sh "sed -i 's/\${ENV}/${ENV}/' ./deploy/Dockerfile"
>
>     sh "sed -i 's/\${PROJECT\_NAME}/${PROJECT\_NAME}/' ./deploy/Dockerfile"
>
>     sh "sed -i 's/\${PROJECT\_FILE}/${PROJECT\_FILE}/' ./deploy/Dockerfile"
>
>     sh "sed -i 's/\${PORT}/${PORT}/' ./deploy/Dockerfile"
>
>     sh\(returnStdout: true, script: "docker login --username=账号 registry.cn-shanghai.aliyuncs.com -pmima"\)
>
>     docker.build\("${BUILD\_TAG}", "-f ./deploy/Dockerfile ."\).push\(\)
>
> }
>
> stage\('DEPLOY'\) {
>
>     withCredentials\(\[kubeconfigFile\(credentialsId: 'aliyun-k8s',variable: 'KUBECONFIG'\)\]\) {
>
>       sh\(returnStdout: true, script: "sed -i 's/\${ENV}/${ENV}/' ./deploy/Deployment.yaml"\)
>
>       sh\(returnStdout: true, script: "sed -i 's/\${PROJECT\_NAME}/${PROJECT\_NAME}/' ./deploy/Deployment.yaml"\)
>
>       sh\(returnStdout: true, script: "sed -i 's/\${PORT}/${PORT}/' ./deploy/Deployment.yaml"\)
>
>       sh\(returnStdout: true, script: "sed -i 's/\${NODE\_PORT}/${NODE\_PORT}/' ./deploy/Deployment.yaml"\)
>
>       sh\(returnStdout: true, script: "sed -i 's/\${VERSION}/v${BUILD\_NUMBER}/' ./deploy/Deployment.yaml"\)
>
>       sh 'kubectl apply -f  ./deploy/Deployment.yaml'
>
>     }
>
> }
> ```
>
> }



