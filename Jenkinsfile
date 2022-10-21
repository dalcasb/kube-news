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

        stage("Push da imagem pro docker hub"){
            steps{
                script {
                    docker.withRegistry('', dockerhub)
                        dockerapp.push('latest')
                        dockerapp.push("${env.BUILD_ID}")
                }
            }
        }
    }
}