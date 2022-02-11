pipeline {
    agent any
    stages {
        stage("Checkout code") {
            steps {
                checkout scm
            }
        }
        stage("deploy") {
            steps {
                sh "kubectl delete service example-service"
                sh "kubectl apply -f Jenkins-demo/example_svc.yaml"
            }
        }
    }
}

