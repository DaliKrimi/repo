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
                sh 'npm install'
            }
        }
    }
}
