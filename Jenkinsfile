pipeline {
    agent any  // Use any agent

    stages {
        stage('Build Angular UI') {
            agent {
                docker 'node:14'  // Docker image for Angular build
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
                docker 'golang:1.19'  // Docker image for Go build
            }
            steps {
                dir('go-backend') {
                    sh 'go build'
                }
            }
        }
    }
}
