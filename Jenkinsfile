pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'git@github.com:jayaprakash-shanmugam/jenkins-tutorial.git'
            }
        }
        stage('Build Angular UI') {
            agent {
                docker {
                    image 'node:14'
                }
            }
            steps {
                dir('angular-frontend') {
                    sh 'npm install'
                    sh 'ng build --prod'
                }
            }
        }
        stage('Build Go Backend') {
            agent {
                docker {
                    image 'golang:1.19'
                }
            }
            steps {
                dir('go-backend') {
                    sh 'go build -o app'
                }
            }
        }
        stage('Run Tests') {
            steps {
                echo 'Running frontend and backend tests (to be implemented)...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying Angular and Go applications (to be implemented)...'
            }
        }
    }
}
