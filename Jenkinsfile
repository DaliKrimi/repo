pipeline {
    agent any

    stages {
        stage('Getting Code') {
            steps {
                checkout scm
            }
        }

        stage('Installing Dependencies') {
            steps {
                tools {
                    nodejs '16'
                }
                sh 'npm install'
            }
        }

        stage('Building Project') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Deploying Code') {
            steps {

                sh 'scp -r build/ ubuntu@107.23.97.95:/etc/nginx/sites-enabled'
            }
        }
    }

    post {
        always {
            // Clean up the workspace
            cleanWs()
        }
    }
}
