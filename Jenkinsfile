pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Jenkins automatically checks out the code from your Git repo
                checkout scm
                echo 'Code checked out from Git!'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                // Add your build commands here if needed, e.g.:
                // sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add test commands here if needed, e.g.:
                // sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add deploy commands here if needed
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
