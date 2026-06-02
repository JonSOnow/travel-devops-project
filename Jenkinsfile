pipeline {
agent any


stages {

    stage('Build Docker Image') {
        steps {
            sh 'docker build --no-cache -t travel-devops-project .'
        }
    }

    stage('Stop Old Container') {
        steps {
            sh 'docker stop travel-container || true'
            sh 'docker rm travel-container || true'
        }
    }

    stage('Run New Container') {
        steps {
            sh 'docker run -d -p 8086:80 --name travel-container travel-devops-project'
        }
    }
}


}
