pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t django-ecommerce .'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing Django application'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment stage'
            }
        }
    }
}