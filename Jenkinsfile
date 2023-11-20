pipeline {
    agent any
    stages {
        
        stage("Code Fetch from Git"){
            steps{
                git url: "https://github.com/robinthakur00/nodejs-todo-app.git", branch: "master"
            }
        }
        stage("Build the code"){
            steps{
                sh "docker build -t nodejs-todo-app . "
            }
        }
        stage("Scan Image with Trivy"){
            steps{
                sh "trivy image nodejs-todo-app"
            }
        }
        stage("Push to DockerHub"){
            steps{
                withCredentials([usernamePassword(credentialsId:"dockerHub",passwordVariable:"dockerHubPass",usernameVariable:"dockerHubUser")]){
                sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
                sh "docker tag nodejs-todo-app:latest ${env.dockerHubUser}/nodejs-todo-app:latest"
                sh "docker push ${env.dockerHubUser}/nodejs-todo-app:latest"
                }
            }
        }
        stage("Deploy the Application"){
            steps{
                sh "docker-compose down && docker-compose up -d"
            }
        }
    }
}
