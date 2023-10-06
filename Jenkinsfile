 pipeline {
    agent {
        node {
            label 'kubeapp'
        }
    }
    stages {
        stage('Clone Repository') {
            steps {
                dir('/home/ubuntu/workspace/aq-1') {
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
                sh 'sudo docker pull abhijeetsingh1/aesthesia:v1'
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

