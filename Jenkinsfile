pipeline {
    agent any

    stages {
        stage('Pull code from git') {
            steps {
                git 'https://github.com/xuanhanhs/jenkins.git'
            }
        }

        stage('Build and push image') {
            steps {
                withDockerRegistry(credentialsId: 'hanh2002', url: ' https://index.docker.io/v1/') {
                    sh 'docker build -t hanh2002/nodejs-test:v10 .'
                    sh 'docker push hanh2002/nodejs-test:v10'
                }
            }
        }
    }
}