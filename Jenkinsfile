
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
                bat 'javac App.java'
            }
        }

        stage('Test') {
            steps {
                bat 'java App'
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
