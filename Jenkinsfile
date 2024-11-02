pipeline {
    agent any  // Use any available agent
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from Git repository
                // checkout scm
            }
        }
        stage('Install Dependencies') {
            steps {
                // Install required Python packages
                sh 'pip install -r requirements.txt || true'
            }
        }
        stage('Run Unit Tests') {
            steps {
                // Run unit tests
                sh 'python -m unittest discover -s . -p "test_*.py"'
            }
        }
    }
    post {
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
