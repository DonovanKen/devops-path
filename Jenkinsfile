library 'jenkins_shared_lib'

pipeline {
    agent any
    parameters {
        string(name: 'IMAGE_FRONTEND_NAME', defaultValue: 'frontend-image', description: 'The name of my frontend image')
        string(name: 'IMAGE_TAG', defaultValue: 'latest', description: 'The tag of my frontend image')
        string(name: 'CONTAINER_NAME', defaultValue: 'fontend-container', description: 'The name of my frontend container')
        string(name: 'DOCKERHUB_USER', defaultValue: 'franklinfoko', description: 'The username of docker hub')
        string(name: 'ACCOUNT_ID', defaultValue: '891377281461', description: 'The ID of AWS account')
        string(name: 'AWS_REGION', defaultValue: 'ca-central-1', description: 'Mys AWS Region')
        
    }
    
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    sh """
                        echo Build Docker Image
                        cd AWS/project/python-three-tier-app/frontend/            
                    """
                    dockerBuild("${params.IMAGE_FRONTEND_NAME}", "${params.ACCOUNT_ID}", "${params.IMAGE_TAG}", "${params.AWS_REGION}", "${params.DOCKERHUB_USER}" )
                }
                
            }
        }
    }
}