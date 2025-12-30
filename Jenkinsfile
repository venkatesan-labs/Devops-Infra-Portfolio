pipeline {
    agent any
    environment {
        dockerImage = 'my-devops-portfolio:latest'
        registryUrl = 'ghcr.io/venkatesan-labs/'
        
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
                withCredentials([usernamePassword(credentialsId: 'GIT_PACKAGE', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                  script {
                    sh 'echo ${PASSWORD} | docker login ghcr.io -u ${USERNAME} --password-stdin'
                    sh "docker tag ${dockerImage} ${registryUrl}${dockerImage}"
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
                    docker run -d -p 8080:80 --name my-running-app ghcr.io/kodecloud95/my-devops-portfolio:latest
                }
            }
        }
    }
}
