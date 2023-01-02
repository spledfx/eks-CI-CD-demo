pipeline {
    agent   any
    
    stages{
        
        stage('Update Deployment') {
       
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'default', contextName: 'default', credentialsId: 'config_k3s', namespace: '', serverUrl: ' https://spl.k3s:6443']]){
                sh 'kubectl apply -f nginx-deploy.yaml -n ci-cd-test'
                }
            }
        }
        stage('Update App') {
       
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'default', contextName: 'default', credentialsId: 'config_k3s', namespace: '', serverUrl: ' https://spl.k3s:6443']]){
                sh 'kubectl create configmap nginx-index-html-configmap -n ci-cd-test --from-file index.html -o yaml --dry-run | kubectl apply -f -'
            }
        }
     }
  }
}
