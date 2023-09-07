pipeline {
    agent any

    stages{
        stage('Geting Code'){
            steps {
                checkout scm
            }
        }

        stage('Installing dependencies'){
            steps {
                tools {
                    nodejs '14'
                }
                sh 'npm install'
            }
        }

        stage('Building project') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Deploying code') {
            steps {
                sh 'scp -r build/ ubuntu@107.23.97.95:/etc/nginx/sites-enabled'
            }
        }
    }
}