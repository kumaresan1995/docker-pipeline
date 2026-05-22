pipeline {
    agent any

    stages {

        stage('Check Files') {
            steps {
                sh 'ls'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp:v1 .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f mycontainer || true'
                sh 'docker run -d -p 9090:80 --name mycontainer myapp:v1'
            }
        }
    }
}