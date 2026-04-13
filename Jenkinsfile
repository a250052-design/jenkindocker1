pipeline {
    agent any

    environment {
        PROJECT_PATH = "D:/Krupa28/ProjectDir/DockerDemo"
        IMAGE_NAME = "my-java-app"
        CONTAINER_NAME = "java-container"
    }

    stages {
        stage('Build Java Application') {
            steps {
                script {
                    bat "javac %PROJECT_PATH%/HelloWorld.java"
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    bat "docker build -t %IMAGE_NAME% %PROJECT_PATH%"
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    bat "docker run --rm --name %CONTAINER_NAME% %IMAGE_NAME%"
                }
            }
        }
    }
}