pipeline{
    agent any

    environment{
        DOCKER_IMAGE = 'bedeneche/cicd-node-api'
        DOCKER_CREDS = 'bede'
        EC2_USER = 'ubuntu'
        // EC2_HOST = 'EC2_PUBLIC_IP_OR_DNS'
        CONTAINER_NAME = 'cicd-node-api'
        APP_PORT = '3000'
      //  EC2_SSH_CREDS = 'ec2-ssh-key'
    }
}  
    stages {

        stage("checkout"){
            steps{
                checkout scm
            }
        }


        stage("install dependencies"){
            steps{
                sh 'npm ci'
            }
        } 

        stage("Test"){
            steps{
                sh 'npm test'
            }
        }   
    }
