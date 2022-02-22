pipeline {

  agent { label 'kubepod' }

  stages {
    stage('deploy') {
      steps {
        withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'kubernetes', contextName: '', credentialsId: 'TestKubernetes', namespace: 'kube-system', serverUrl: '']]) {
          kubectl apply -f nginx.yaml
        }
      }
    }
  }
}
