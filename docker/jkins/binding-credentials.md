# binding-credentials

> [https://www.jenkins.io/doc/pipeline/steps/credentials-binding/](https://www.jenkins.io/doc/pipeline/steps/credentials-binding/)
>
> [https://stackoverflow.com/questions/59770591/how-to-access-the-application-after-the-kubernetes-deployment](https://stackoverflow.com/questions/59770591/how-to-access-the-application-after-the-kubernetes-deployment)

## k8s

> ```
> node {
>   stage('Apply Kubernetes files') {
>     withCredentials([kubeconfigFile(credentialsId: 'alik8s',variable: 'KUBECONFIG')]) {
>       sh 'kubectl get namespaces'
>     }
>   }
> }
> ```





