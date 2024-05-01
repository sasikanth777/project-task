pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('boilerplate-express:latest')
                }
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                script {
                    // Use kubectl to apply Kubernetes manifest files
                    sh 'kubectl apply -f your-kubernetes-manifest.yaml'
                }
            }
        }
    }
}
