pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "yourdockerhub/devops-demo"
    }

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/yourusername/devops-cicd-kubernetes-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }

        stage('Push Docker Image') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'USER', passwordVariable: 'PASS')]) {
                    sh 'docker login -u $USER -p $PASS'
                    sh 'docker push $DOCKER_IMAGE'
                }
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f kubernetes/'
            }
        }
    }
}