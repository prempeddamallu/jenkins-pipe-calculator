pipeline {
    agent {
        docker {
            image 'python:3.8' // Use an appropriate Docker image
            args '-u root:root' // Optional: run as root
        }
    }
    stages {
        stage('CI') {
            steps {
                // Install dependencies if any
                sh 'pip install unittest' // Add more if you have requirements
                // Run unit tests
                sh 'python -m unittest test_calculator.py'
            }
        }
    }
}
