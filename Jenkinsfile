pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                // Jenkins handles the Git clone automatically if this is a 'Pipeline from SCM'
                echo 'Source code has been checked out.'
            }
        }

        stage('Run Python Script') {
            steps {
                script {
                    // We use the absolute path to Python 3.10 that you provided
                    // Note the double backslashes (\\) required for Windows paths in Groovy
                    def pythonPath = 'C:\\Users\\Rishitha\\AppData\\Local\\Programs\\Python\\Python310\\python.exe'
                    
                    echo "Starting Python script using: ${pythonPath}"
                    
                    // Optional: Install dependencies if you have a requirements.txt
                    // bat "${pythonPath} -m pip install -r requirements.txt"
                    
                    // Run your application
                    bat "\"${pythonPath}\" app.py"
                }
            }
        }
    }
    
    post {
        always {
            echo 'Build process completed.'
        }
        failure {
            echo 'The Python script failed. Check the console output for specific tracebacks.'
        }
    }
}
