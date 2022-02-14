pipeline {

  agent { label 'kubeagent' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/SLHolmess/Jenkins-demo', branch:'main'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "example_svc.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}
