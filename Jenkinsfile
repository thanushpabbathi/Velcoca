pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                bat 'echo Building Velcoca application...'
            }
        }

        stage('Test') {
            steps {
                bat 'echo Testing Velcoca application...'
            }
        }
        stage('Deploy') {
        steps {
                bat 'echo Deploying Velcoca website...'
                bat 'echo Website deployed successfully!'
            }
        }
    }
}