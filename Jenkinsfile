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
    }
}
