pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID = credentials('aws-creds')
        AWS_SECRET_ACCESS_KEY = credentials('aws-creds')
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', credentialsId: 'github-ssh-key', url: 'git@github.com:abageshwar/terraformapply.git'
            }
        }
        stage('Infrastructure Deployment') {
            steps {
                sh 'terraform init'
                sh 'terraform apply -auto-approve'
            }
        }
    }
}
