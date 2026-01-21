pipeline {
    agent {
        docker {
            image 'python:3.11-slim'
        }
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Python Version') {
            steps {
                sh 'python --version'
            }
        }

        stage('Run Application') {
            steps {
                sh 'python app.py'
            }
        }

        stage('Run Checks') {
            steps {
                sh 'python check.py'
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully ✅'
        }
        failure {
            echo 'Build failed ❌'
        }
    }
}
