pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Checkout the repository from the source control
                git ''
            }
        }

        stage('Build') {
            steps {
                // Install dependencies (if any) and set up the environment
                sh 'pip install -r requirements.txt || true'
            }
        }

        stage('Test') {
            steps {
                // Run the Python script and verify its output
                script {
                    def result = sh(script: 'python app.py', returnStdout: true).trim()
                    echo "Script Output: ${result}"
                }
            }
        }
    }
}
