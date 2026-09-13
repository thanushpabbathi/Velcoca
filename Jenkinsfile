pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Test') {
            steps {
                sh 'echo "Testing Velcoca application..."'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t velcoca .'
            }
        }

        stage('Remove Old Container') {
            steps {
                sh 'docker rm -f velcoca-container || true'
            }
        }

        stage('Docker Run') {
            steps {
                sh 'docker run -d -p 8081:80 --name velcoca-container velcoca'
            }
        }

        stage('Health Check') {
            steps {
                sh 'curl -f http://localhost:8081'
            }
        }
    }
}   