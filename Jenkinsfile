pipeline{
    agent any

    stages{
        stage('Code'){
            steps{
                echo 'cloning the code'
                git url: "https://github.com/shivamsharma20work-afk/simple-web.git", branch: "main"
            }
        }
        stage('Build') {
            steps{
                echo 'cloning the frontend code'
                sh 'docker build -t simple .'
            }
        }
        stage('Push to Dockerhub') {
            steps{
                echo 'Pushing this Image to Docker Hub'
                withCredentials([usernamePassword('credentialsId': "dockerhubcreds" ,
                passwordVariable:"dockerHubPass",
                usernameVariable:"dockerHubUser")]){
                sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
                sh 'docker image tag simple:latest shivam011/simple:latest'
                sh 'docker push ${env.dockerHubUser}/simple:latest'
                }
            }
        }
        stage('Test') {
            steps{
                echo 'Testing the code'
            }
        }
        stage('Deploy') {
            steps{
                echo 'Deploying the code'
                sh 'docker compose up -d '
            }
        }
    }
}