pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/SRCEM-AIML/C06_DewanshWarjurkar_assignment2.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    try {
                        bat 'docker build -t dewanshhh24/studentproject .'
                    } catch (Exception e) {
                        error "Docker build failed: ${e}"
                    }
                }
            }
        }
        stage('Push to Docker Hub') {
            steps {
                script {
                    try {
                        withDockerRegistry(credentialsId: 'docker-hub-credentials') {
                            bat 'docker push dewanshhh24/studentproject'
                        }
                    } catch (Exception e) {
                        error "Docker push failed: ${e}"
                    }
                }
            }
        }
    }
}