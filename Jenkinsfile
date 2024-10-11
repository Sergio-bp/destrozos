pipeline {
    agent any
    tools {
        go 'go'
    }

    environment{
        GO111MODULE='on'
    }

    stages{
        stage('Test'){
            steps{
                git 'https://github.com/AdminTurnedDevops/go-webapp-sample.git'
                sh 'go test ./...'
            }
        }
        stage('Build'){
            steps{
                git 'https://github.com/AdminTurnedDevops/go-webapp-sample.git'
                sh 'go build .'
            }
        }
        stage('Run'){
            steps{
                sh 'cd /var/jenkins_home/go-full-pipeline && go-webapp-sample &'
            }
        }
    }
}