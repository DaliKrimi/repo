pipeline {
    agent any
    tools {nodejs "nodejs"}
    stages {
        stage('Getting Code') {
            steps {
                checkout scm
            }
        }

        stage('Installing Dependencies') {
            steps {
                sh 'npm install'
            }
        }
         stage('Building Project') {
            steps {
                sh 'npm --depth 20 update --save caniuse-lite browserslist'
                sh 'npm run build'
            }
        }

        stage('Deploying Code') {
            steps {

                sh 'sudo scp -r build/ ubuntu@107.23.97.95:/var/www/'
            }
        }
    }
}
