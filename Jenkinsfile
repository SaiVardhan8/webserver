pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/SaiVardhan8/webserver.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t web-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f web-container || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8081:80 --name web-container web-app'
            }
        }
    }
}
