pipeline {
  agent any
  stages {
    stage('Build Application') { 
      steps {
        bat 'mvn clean install'
      }
    }
 	stage('Test') { 
      steps {
        echo 'Test Appplication...' 
        bat 'mvn test'
      }
    }
 	
   
	stage('Deployment') { 
      environment {
	ANYPOINT_CREDENTIALS = credentials('anypointPlatform')
        ENVIRONMENT = 'dev'
        APP_NAME = 'uho-dev-sapi'
	
      }
            
      steps {
        echo 'Deploying only because of code commit...'
        echo 'Deploying to  dev environent....'
        bat 'mvn package deploy -DmuleDeploy -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -Denc.key=${Denc.key} -Danypoint.platform.client_id=${Danypoint.platform.client_id} -Danypoint.platform.client_secret=${Danypoint.platform.client_secret} -Danypoint.environment=${ENVIRONMENT}  -DAPP_NAME=${APP_NAME}'
      
      }
	  
	}
  }
}
