pipeline {
    agent {
        docker {
            image 'node:14'
        }
    }
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'sudo npm install'
            }
        }
        // Other stages...
    }
}
