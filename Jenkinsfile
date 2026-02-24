pipeline {
    agent any

    environment {
        // Use python3 (make sure Python is installed on Jenkins agent)
        PYTHON = 'python3'
    }

    stages {
        stage('Checkout') {
            steps {
                // Pull code from Git
                checkout scm
                echo 'Code checked out from Git!'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                // Create virtual environment and install Python dependencies
                sh '''
                    ${PYTHON} -m venv venv
                    source venv/bin/activate
                    pip install --upgrade pip
                    # Add required packages if any, e.g.,
                    # pip install requests
                '''
            }
        }

        stage('Run Python Script') {
            steps {
                echo 'Running Python script...'
                sh '''
                    source venv/bin/activate
                    ${PYTHON} app.py
                '''
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
