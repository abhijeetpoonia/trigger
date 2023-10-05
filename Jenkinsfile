pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                dir('/var/lib/jenkins/workspace/aew') {
                    script {
                        git branch: 'master',
                            url: 'https://github.com/abhijeetpoonia/trigger.git',
                            credentialsId: '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'
                    }
                }
            }
        }
        stage('Build Image') {
            steps {
                sh 'docker pull abhijeetsingh1/aesthesia:v1'
            }
        }
        stage('Check and Remove Container') {
            steps {
                sh 'docker stop my-container || true'
                sh 'docker rm my-container || true'
            }
        }
        stage('Create Container') {
            steps {
                sh 'docker run -d --name my-container -p 8000:8000 abhijeetsingh1/aesthesia:v1'
            }
        }
    }
}
 
