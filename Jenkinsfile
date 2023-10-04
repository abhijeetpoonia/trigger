pipeline {
    agent any
    stages {
        stage('Build Image') {
            steps {
                sh 'docker pull abhijeetsingh1/aesthesia:v1'
            }
        }
        stage('Create Container') {
            steps {
                sh 'docker run -d --name my-container -p 8080:80 abhijeetsingh1/aesthesia:v1'
            }
        }
    }
} 
