pipeline {
    agent any 
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/reigen002/my--python-app.git'
            }
        }
        stage('Setup Environment') {
            steps {
                echo 'Creating virtual environment...'
                bat '"C:\\Users\\MY PC\\AppData\\Local\\Microsoft\\WindowsApps\\python.exe" -m venv venv'
                bat 'venv\\Scripts\\activate'
                bat '"C:\\Users\\MY PC\\AppData\\Local\\Microsoft\\WindowsApps\\python.exe" -m pip install -r requirements.txt'
            }
        }
        stage('Run Tests') {
            steps {
                bat '"C:\\Users\\MY PC\\AppData\\Local\\Microsoft\\WindowsApps\\python.exe" train_model.py'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add your deployment steps here
            }
        }
    }
    post {
        always {
            echo 'Cleaning up workspace...'
            cleanWs()
        }
    }
}
