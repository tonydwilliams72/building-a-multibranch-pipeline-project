pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-u 0:0'
            args '-p 3000:3000 -p 5000:5000'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage ('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage ('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}
