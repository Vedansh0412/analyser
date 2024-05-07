pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Add commands to build your Python application (if applicable)
                sh 'pip install -r requirements.txt'  // Install Python dependencies
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
                // Deploying the Python application
                script {
                    // Assuming you have a deployment script named deploy.sh
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
        }
    }
}
