pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/jayaprakash-shanmugam/jenkins-tutorial.git'
            }
        }
        stage('Build Angular Frontend') {
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
                script {
                    // Example test steps can be added here for Angular and Go
                    echo 'Running tests...'
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Add deployment logic here
            }
        }
    }
}
