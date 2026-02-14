pipeline{
    agent any

    stages{
        stage('Code'){
            steps{
                echo 'cloning the code'
            }
        }
        stage('Build backend') {
            steps{
                echo 'cloning the backend code'
            }
        }
        stage('Build frontend') {
            steps{
                echo 'cloning the frontend code'
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
            }
        }
    }
}