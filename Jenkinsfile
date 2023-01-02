pipeline {
    agent   any
    
    stages{
        
        stage('List ns') {
       
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'default', contextName: 'default', credentialsId: 'config_k3s', namespace: '', serverUrl: ' https://spl.k3s:6443']]){
                sh 'kubectl apply -f nginx-deploy.yaml -n ci-cd-test'
            }
        }
     }
  }
}
