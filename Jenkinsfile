pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Build Docker Image') {
            steps {
                timeout(time: 10, unit: 'MINUTES') {
                    sh 'docker build -t myapp:latest .'
                }
            }
        }
        
        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 8080:8080 myapp:latest'
            }
        }
    }
}