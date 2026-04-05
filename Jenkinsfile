@Library("shared") _
pipeline{
    
    agent {label "vinod"}
    
    stages{
        
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        
        stage("Code"){
            steps{
                script{
                    clone("https://github.com/milinddeore1111-afk/django-notes-app.git","main")
                }
            }
        }
        
        stage("Build"){
            steps{
                script{
                    docker_build("notes-app","latest","miilinddevops")
                }

            }
        }
        
        stage("Push"){
            steps{
                script{
                    docker_push("notes-app","latest")
                }
                }
            }
            
        
        
        stage("Deploy"){
            steps{
            echo "this is deploying the code"
            sh "docker compose up -d"
            echo "code deployed successfully"
            }
        }
        
    }
}
