pipeline {
    agent any
    stages {
        stage("Build Docker Image") {
            steps {
                bat 'C:\\Windows\\System32\\cmd.exe /c docker build --no-cache -t vite-app .'
            }
        }
        stage('Deploy Container') {
            steps {
                bat '''
                C:\\Windows\\System32\\cmd.exe /c docker stop vite-container || echo Container not working
                C:\\Windows\\System32\\cmd.exe /c docker rm vite-container || echo Container not found
                C:\\Windows\\System32\\cmd.exe /c docker run -d -p 8001:80 --name vite-container vite-app
                '''
            }
        }
    }
}