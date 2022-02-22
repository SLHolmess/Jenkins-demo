pipeline {

  agent { label 'kubepod' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/SLHolmess/Jenkins-demo', branch:'main'
      }
    }

    stage('deploy') {
      steps {
        withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'kubernetes', contextName: '', credentialsId: 'TestKubernetes', namespace: 'kube-system', serverUrl: 'https://10.0.2.15:6443']]) {
          kubectl get pod
        }
      }
    }
  }
}
