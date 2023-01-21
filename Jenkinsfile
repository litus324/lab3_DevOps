pipeline {
    agent any
    stages {
        stage('Clone'){
            steps{
                git credentialsId: 'github', url: 'https://github.com/litus324/lab3_devOps.git'
            }   
        }
        stage('Build'){
            steps{
                 withDockerRegistry(credentialsId: 'docker', url: 'https://index.docker.io/v1/') {
                    bat 'docker build -t 20120324/devops:v1 -f Dockerfile .'
                    bat 'docker push 20120324/devops:v1'
                }
            }
        }
    }
}