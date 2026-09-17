pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Generate Report') {
            steps {
                // Change 'bat' to 'sh' if your Jenkins server runs on Linux/macOS
                bat 'python app.py' 
            }
        }
        stage('Archive Report') {
            steps {
                archiveArtifacts artifacts: 'report.txt', fingerprint: true
            }
        }
    }
}
