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

        stage('Docker Build') {
            steps {
                bat 'docker build -t velcoca .'
            }
        }

        stage('Remove Old Container') {
            steps {
                bat 'docker rm -f velcoca-container || exit 0'
            }
        }

        stage('Docker Run') {
            steps {
                bat 'docker run -d -p 8081:80 --name velcoca-container velcoca'
            }
        }
    }
}