pipeline {
    agent any
    tools{
        maven 'maven-3.9.9'
    }
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/chetanmanne/devops-automation']]])
                sh 'mvn clean install'
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t chetanmanne/devops-integration .'
                }
            }
        }
    }
 }
