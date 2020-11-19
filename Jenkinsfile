pipeline {
    agent any
    environment{
        DOCKER_TAG = getDockerTag()
    }
    stages{
        stage('Build Docker Image'){
            steps{
                sh "docker build . -t tbalaji/docker:${DOCKER_TAG}"
            }
        }
        stage('Docker Image Push'){
            steps{
               
                    sh "docker login -u tbalaji -p Balajibala"
                   sh "docker push tbalaji/docker:${DOCKER_TAG}"
                
            }
        }
    }
}

def getDockerTag(){
    def tag  = sh script: 'git rev-parse HEAD', returnStdout: true
    return tag
}
