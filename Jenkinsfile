pipeline{
    agent any
    
    stages{
        stage("code"){
            steps{
                echo "cloing the code "
                git url:"https://github.com/Satankumaryadav/Note-App.git", branch: "master"
            }
            
        }
        stage("build"){
            steps{
                echo "build the image "
                sh "docker build -t note-app-sky1 ."
                
            }
            
        }
        stage("push to dockerhub"){
            steps{
                echo "pushing image to the dockerhub "
                
                withCredentials([usernamePassword(credentialsId:"dockerHub", passwordVariable:"dockerhubPass", usernameVariable:"dockerhubUser")]){
                    sh "docker tag note-app-sky1 ${env.dockerhubUser}/note-app-sky1:latest"
                    sh "docker login -u ${env.dockerhubUser} -p ${env.dockerhubPass}"
                    sh "docker push ${env.dockerhubUser}/note-app-sky1:latest"
                }
            }
            
        }
        stage("deploy"){
            steps{
                echo "deploying the container "
                sh "docker-compose down && docker-compose up -d"
                
            }
            
        }
    }
}
