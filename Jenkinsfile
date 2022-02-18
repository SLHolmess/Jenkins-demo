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
        withKubeConfig([credentialsId: 'kubernetes-config']) {
        sh 'curl -LO "https://storage.googleapis.com/kubernetes-release/release/v1.20.5/bin/linux/amd64/kubectl"'  
        sh 'chmod u+x ./kubectl'  
        sh './kubectl apply -f nginx.yaml'
        }
      }
    }
    
  }

}
