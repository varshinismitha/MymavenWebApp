pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/varshinismitha/MymavenWebApp.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.war', fingerprint: true
            }
        }

    }

    post {
        success {
            echo 'Build SUCCESS 🎉'
        }
        failure {
            echo 'Build FAILED ❌'
        }
    }
}

