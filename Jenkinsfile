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
                 container ('jnlp') {
                      withCredentials([
                          kubeconfigFile(
                          credentialsId: mykubeconfig,
                          variable: 'KUBECONFIG')
                          ]) {
                          sh 'envsubst < deploy/all-in-one/nginx.yaml | kubectl apply -f -'
                      }
                 }
             }
        }
    
  }

}
