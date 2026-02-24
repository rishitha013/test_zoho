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
                bat 'python app.py'
            }
        }
    }
}
