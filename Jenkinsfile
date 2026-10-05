pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                checkout scm
            }
        }
        stage('Deploy to K8s') {
            steps {
                echo 'Deploying to Kubernetes cluster...'
                sh 'kubectl apply -f k8s/'
            }
        }
    }
}
