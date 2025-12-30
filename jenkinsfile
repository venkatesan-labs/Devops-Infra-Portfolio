pipeline {
    agent any
    environment {
        dockerImage = 'my-devops-portfolio:latest'
        registryUrl = 'ghcr.io/kodecloud95/'
        
    }
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    sh "docker build -t ${dockerImage} ."
                }
            }
        }
        stage('Push Docker Image') {
            steps {
                withcredentials([usernamePassword(credentialsId: 'GIT_PACKAGE', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                  script {
                    sh "echo $PASSWORD | docker login ${registryUrl} -u $USERNAME --password-stdin"
                    sh "docker push ${registryUrl}${dockerImage}"
                    }
                }
            }
        }
        stage('Deploy Application') {
            steps {
                script {
                    // Deployment logic goes here
                    echo "Deploying ${dockerImage} to the environment"
                }
            }
        }
    }
}