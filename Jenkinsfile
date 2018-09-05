pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
				bat 'mvn clean install' 
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying to PCF'
				
				pushToCloudFoundry(
    target: 'api.run.pivotal.io',
    organization: 'com.rajan',
    cloudSpace: 'development',
    credentialsId: 'myPCF'
   
)
            }
        } 
    }
}