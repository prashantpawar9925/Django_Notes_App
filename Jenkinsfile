@Library("Shared") _
pipeline{
    agent {label "prashant"}
    
    stages{
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("code"){
            steps{
                script{
                clone("https://github.com/prashantpawar9925/Django_Notes_App.git","main")
                }
                
            }
        }
        stage("Build"){
            steps{
                script{
                    docker_build("notes-apps","latest","prashant9025")
                }
                
            }
        }
        stage("Push"){
            steps{
                script{
                    docker_push("notes-apps","latest","prashant9025")
                }
                
            }
        }
        stage("Deploy"){
            steps{
                echo "This is deploying the code."
                sh "docker compose up -d"
            }
        }
    }
}
