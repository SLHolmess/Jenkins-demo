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
                sh "kubectl delete -f example_svc.yaml"
                sh "kubectl apply -f example_svc.yaml"
            }
        }
    }
}

