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
        stage('Create Container') {
            steps {
                sh 'docker run -d --name my-container -p 8000:8000 abhijeetsingh1/aesthesia:v1'
            }
        }
    }
}
 
