pipeline {
    agent any

    options {
        timestamps()
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Verify Tools') {
            steps {
                sh 'git --version'
                sh 'python --version'
            }
        }

        stage('Python Syntax Check') {
            steps {
                sh 'python -m py_compile program1.py'
            }
        }

        stage('Build Complete') {
            steps {
                sh 'Jenkins pipeline completed successfully.'
            }
        }
    }

    post {
        success {
            sh 'Build passed.'
        }
        failure {
            sh 'Build failed. Check the console output.'
        }
    }
}
