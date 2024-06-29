pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the repository
                checkout https://github.com/Varshini0051/jenkins_test.git
            }
        }

        stage('Setup Python') {
            steps {
                // Install Python environment (assuming you are using a Unix-like system)
                sh 'python3 -m venv venv'
                sh 'source venv/bin/activate'
                sh 'pip install --upgrade pip'
            }
        }

        stage('Run Test') {
            steps {
                // Run the Python script
                sh 'source venv/bin/activate && python test.py'
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
