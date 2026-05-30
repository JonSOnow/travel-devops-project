pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build --no-cache -t travel-devops-project .'
            }
        }

        stage('Stop Old Container') {
            steps {
                bat 'docker stop travel-container || exit 0'
                bat 'docker rm travel-container || exit 0'
            }
        }

        stage('Run New Container') {
            steps {
                bat 'docker run -d -p 8086:80 --name travel-container travel-devops-project'
            }
        }
    }
}
