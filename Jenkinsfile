
pipeline {
    agent any
    tools {
       terraform('terraform') 
    }
    stages {
        stage('Git checkout') {
           steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Shubh1am/terraform_ec2_public.git']])
            }
        }
        stage('terraform init command') {
            steps{
                sh 'terraform init'
            }
        }
        stage('terraform plan') {
            steps{
                sh 'terraform plan'
            }
        }
        stage('terraform apply') {
            steps{
                sh 'terraform apply --auto-approve'
            }
        }
    }
}
