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
        stage('Test') {
            steps{
                echo 'Testing the code'
            }
        }
        stage('Deploy') {
            steps{
                echo 'Deploying the code'
                sh 'docker run -d -p 3000:3000 simple'
            }
        }
    }
}