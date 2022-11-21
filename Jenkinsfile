pipeline {
    agent {
        docker {
            image 'node:lts-alpine'
            args '-p 3000:3000 -p 4200:4200' 
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}