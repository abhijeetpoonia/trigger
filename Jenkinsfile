pipeline {
    agent any
    stages {
        stage('clone repository') {
            steps {
                dir('/var/lib/jenkins/workspace/aew') {
                    git branch: 'master',
                        url: 'https://github.com/abhijeetpoonia/trigger.git',
                        credentialsId: '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'
                }
            }
        }
        stage('Build Image') {
            steps {
                sh 'docker pull abhijeetsingh1/aesthesia:v1'
            }
        }
        stage('check-container') {
            steps {
                sh 'docker stop my-container && docker rm my-container'
            }
        }

        stage('Create Container') {
            steps {
                sh 'docker run -d --name my-container -p 8000:8000 abhijeetsingh1/aesthesia:v1'
            }
        }
    }
}
 
