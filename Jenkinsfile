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
        container ('base') {
          sh '''
          kubectl apply -f nginx.yaml
          '''
        }
      }
    }
    
  }

}
