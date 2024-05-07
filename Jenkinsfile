pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'pip install -r requirements.txt'  // Install Python dependencies
            }
        }
        stage('Test') {
            steps {
                sh 'python -m unittest discover tests'  // Run tests
            }
        }
        stage('Deploy') {
            steps {
                // Add deployment steps here
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
