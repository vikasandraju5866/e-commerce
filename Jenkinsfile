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
                bat 'docker build -t django-ecommerce .'
            }
        }

        stage('Deploy') {
            steps {
                bat '''
                docker rm -f ecommerce-container 2>nul || echo No existing container
                docker run -d --name ecommerce-container -p 8000:8000 django-ecommerce
                '''
            }
        }
    }
}