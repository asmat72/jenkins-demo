pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("myapp:${env.BUILD_ID}")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    dockerImage.run("-p 3000:3000")
                }
            }
        }
    }
}
