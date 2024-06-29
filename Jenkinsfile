pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Correct way to checkout the repository
                checkout scm
            }
        }

        stage('Setup Python') {
            steps {
                // Install Python environment (assuming you are using a Unix-like system)
                sh 'python3 -m venv venv'
                // Activate the virtual environment using '.' instead of 'source'
                sh '. venv/bin/activate && pip install --upgrade pip'
            }
        }

        stage('Run Test') {
            steps {
                // Run the Python script within the virtual environment
                sh '. venv/bin/activate && python test.py'
            }
        }
    }

    post {
        always {
            // Cleanup the Python environment
            sh 'rm -rf venv'
        }
    }
}
