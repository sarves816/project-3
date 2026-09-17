pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/sarves816/project-3.git'
            }
        }

        stage('Parallel Tests') {
            parallel {
                stage('Frontend Tests') {
                    steps {
                        bat 'python frontend_check.py'
                    }
                }

                stage('Backend Tests') {
                    steps {
                        bat 'python backend_check.py'
                    }
                }
            }
        }
    }
}
