pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Cloning GitHub repository'
                checkout scm
            }
        }

        stage('Python Version') {
            steps {
                sh 'python3 --version || python --version'
            }
        }

        stage('Run Application') {
            steps {
                sh 'python3 app.py || python app.py'
            }
        }

        stage('Run Checks') {
            steps {
                sh 'python3 check.py || python check.py'
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
