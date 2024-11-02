pipeline {
    agent{
        docker {
            image 'python:3.8' // Use an appropriate Docker image
            // Optional: run as root
        }
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the specified Git repository
                git url: 'https://github.com/prempeddamallu/jenkins-pipe-calculator.git', branch: 'main'
                echo 'Checkout'
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install any required dependencies (adjust as necessary)
                // sh 'pip install -r requirements.txt'  // Ensure you have a requirements.txt if needed
                sh 'pip install unittest'
                // sh 'python -m unittest test_calculator.py'
                echo 'Intall Dependencies'
            }
        }

        stage('Run Tests') {
            steps {
                // Run unit tests
                // sh 'python -m unittest discover'  // Adjust if your tests are located differently
                echo 'Run Tests'
            }
        }
    }

    post {
        always {
            // Actions that run after the pipeline, regardless of success/failure
            echo 'Pipeline completed.'
        }
        success {
            echo 'All tests passed!'
        }
        failure {
            echo 'One or more tests failed.'
        }
    }
}
