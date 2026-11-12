
pipeline {
    agent any
    triggers {
        githubPush()
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                bat 'javac -version'
                bat 'javac app.java'
            }
        }

        stage('Test') {
            steps {
                bat 'java app'
            }
        }
    }

    post {
        success {
            echo 'Build stable'
        }
        failure {
            echo 'Build failed'
        }
    }
}
