pipeline {
    agent any
    stages {
        stage('Fetch Code from GitHub') {
            steps {
                // Checkout code from GitHub repository using credentials
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/master']], // Specify the branch you want to build
                    doGenerateSubmoduleConfigurations: false,
                    extensions: [[$class: 'CleanBeforeCheckout'], [$class: 'CheckoutOption', timeout: 60]],
                    submoduleCfg: [],
                    userRemoteConfigs: [[
                        credentialsId: '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',
                        url: 'https://github.com/abhijeetpoonia/trigger.git' 
                    ]]
                ])
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
 
