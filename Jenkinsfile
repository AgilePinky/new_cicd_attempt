pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build and Run Tests') {
            steps {
                sh 'docker compose up --build --abort-on-container-exit'
            }
        }
    }

    post {
        always {
            sh 'docker compose down'
        }
    }
}