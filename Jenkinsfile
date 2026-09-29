pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Check Files') {
            steps {
                sh 'ls -la'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t realestate-website:build-${BUILD_NUMBER} .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'IMAGE_TAG=build-${BUILD_NUMBER} docker compose up -d'
            }
        }
    }
}
