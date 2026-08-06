pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Docker Build') {
            steps {
                sh 'docker build -t snapcart:v1 .'
            }
        }
    }
    post {
        success {
            echo 'SnapCart image built successfully.'
        }
        failure {
            echo 'Pipeline failed. Check the console output.'
        }
    }
}
