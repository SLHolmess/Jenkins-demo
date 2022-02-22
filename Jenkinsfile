pipeline {

  agent { label 'kubepod' }

  stage('deploy') {
     steps {
       withKubeCredentials(kubectlCredentials: [[caCertificate: '', 
       clusterName: 'kubernetes', contextName: '', credentialsId: 'TestKubernetes', namespace: 'kube-system', 
       serverUrl: 'https://192.168.10.10:6443']]){
         kubectl apply -f nginx.yaml
       }
     }
  }
}
