pipeline {
    agent {
        docker {
            image 'node:14'
        }
    }
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        // Other stages...
    }
}
