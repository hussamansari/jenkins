pipeline {
    agent any
    
    stages {
        stage("Compose Down"){
            steps {
                sh 'sudo docker-compose down'
            }
        }
        stage('reset workspace'){
            steps {
                sh 'sudo rm -rf *'
            }
        }
        stage('Git clone') {
            steps {
              sh 'sudo git clone https://github.com/Armaan-zaheer/pipeline-jenkins.git'
            }
        }
        stage('Install Dependencies'){
            steps{
                sh 'sudo npm init --yes'
            }
        }
        stage('npm install'){
            steps{
                sh 'sudo npm install express --save'
            }
        }
        stage('Build App'){
            steps{
                sh "sudo cp ./pipeline-jenkins/docker-compose.yml . | sudo cp ./pipeline-jenkins/Dockerfile . | sudo cp ./pipeline-jenkins/server.js . "
                sh "sudo docker-compose up -d"
            }
        }
    }
}
