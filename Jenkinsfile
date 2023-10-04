peline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                // The workspace directory will be used by default
                git branch: 'master',
                    url: 'https://github.com/abhijeetpoonia/aesthesia.git',
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
 
