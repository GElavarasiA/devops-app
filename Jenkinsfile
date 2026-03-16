pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/yourusername/devops-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t devops-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                bat 'docker stop devops-container'
                bat 'docker rm devops-container'
            }
        }

        stage('Run New Container') {
            steps {
                bat 'docker run -d -p 8081:80 --name devops-container devops-app'
            }
        }

    }
}