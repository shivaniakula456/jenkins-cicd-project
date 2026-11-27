pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/shivaniakula456/jenkins-cicd-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-web-app .'
            }
        }

        stage('Deploy Application') {
            steps {
                sh 'docker rm -f my-web-app || true'
                sh 'docker run -d --name my-web-app -p 8082:80 my-web-app'
            }
        }
    }
}
