pipeline {
    agent any
        docker {
            image 'node:14'

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'sudo apt install npm'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }

        stage('Build') {
            steps {
                script {
                    docker.build('boilerplate-express:latest .')
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
