pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/JEYAPRAKASH21/my-node-devops-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t nodeapp .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop nodeapp || true'
                sh 'docker rm nodeapp || true'
                sh 'docker run -d -p 80:3000 --name nodeapp nodeapp'
            }
        }
    }
}
