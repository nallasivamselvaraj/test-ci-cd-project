pipeline {
    agent any

    environment {
        PROJECT_REPO = "https://github.com/nallasivamselvaraj/my_python_project.git"
    }

    stages {
        stage('Checkout Project') {
            steps {
                git branch: 'master', 
                    url: "${PROJECT_REPO}"
            }
        }

        stage('List Files in Workspace') {
            steps {
                script {
                    bat 'dir /s'  // Lists all files to verify hello.py exists
                }
            }
        }

        stage('Run Python Script') {
            steps {
                script {
                    bat 'python src/hello.py'
                }
            }
        }
    }

    post {
        success {
            echo 'Python script executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
