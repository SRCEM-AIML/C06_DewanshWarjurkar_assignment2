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
                sh 'docker build -t studentproject .'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub', 
                    usernameVariable: 'DOCKER_USER', 
                    passwordVariable: 'DOCKER_PASS'
                )]) {
                    sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin'
                    sh 'docker tag studentproject dewanshhh24/studentproject:latest'
                    sh 'docker push dewanshhh24/studentproject:latest'
                }
            }
        }
    }
}
