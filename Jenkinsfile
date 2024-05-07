pipeline {
    agent any
    
    stages {
        stage('Setup') {
            steps {
                script {
                    // Create and activate a virtual environment
                    sh 'python3 -m venv venv'
                    sh 'source venv/bin/activate'
                }
            }
        }
        stage('Build') {
            steps {
                script {
                    // Install required dependencies using pip
                    sh 'pip install -r requirements.txt'
                }
            }
        }
        stage('Test') {
            steps {
                // Add commands to run tests for your Python application
                sh 'python -m unittest discover tests'
            }
        }
        stage('Deploy') {
            steps {
                script {
                    // Deploying the Python application
                    sh './deploy.sh'
                }
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
        always {
            echo 'Pipeline finished.'
            // Deactivate the virtual environment
            sh 'deactivate'
        }
    }
}
