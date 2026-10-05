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
                sh '''
                    if [ -f k8s/namespace.yaml ]; then
                        kubectl apply -f k8s/namespace.yaml
                    fi
                    kubectl apply -f k8s/
                '''
            }
        }
    }
}
