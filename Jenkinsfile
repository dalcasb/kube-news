pipeline{
    agent any
    stages{
        stage("Build Docker Image"){
            steps{
                script {
                    dockerapp = docker.build("brunodalcas/kube-news:${env.BUILD_ID}", '-f ./src/Dockerfile ./src')
                }
            }

        }
    }
}