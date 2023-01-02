pipeline {
    agent   any
  stages{
  stage('List ns') {
    withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'default', contextName: 'default', credentialsId: 'config_k3s', namespace: '', serverUrl: ' https://spl.k3s:6443']]){
      
        steps {
            
                sh 'kubectl get ns'
            
            }
    }
  }
}
}
