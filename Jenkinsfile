peline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                // The workspace directory will be used by default
                git branch: 'master',
                    url: 'https://github.com/abhijeetpoonia/trigger.git',
                    credentialsId: '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'
            }
        }
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
 
