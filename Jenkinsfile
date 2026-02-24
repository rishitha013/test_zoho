pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning repository...'
            }
        }

        stage('Run Python Script') {
            steps {
                // Use 'bat' because Jenkins is on Windows
                bat 'python app.py'
            }
        }
    }
}
