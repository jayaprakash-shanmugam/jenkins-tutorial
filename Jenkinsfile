pipeline {
    agent any
    stages {
        stage('Build Angular UI') {
            agent {
                docker 'node:14'
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
                docker 'golang:1.19'
            }
            steps {
                dir('go-backend') {
                    sh 'go build'
                }
            }
        }
    }
}
