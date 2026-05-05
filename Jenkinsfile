pipeline {
    agent any

    environment {
        APP_NAME = "web-app"
    }

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t $APP_NAME .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f $APP_NAME || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8081:80 --name $APP_NAME $APP_NAME'
            }
        }
    }
}
