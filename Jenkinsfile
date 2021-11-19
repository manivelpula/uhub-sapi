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
        bat 'mvn clean package deploy -DmuleDeploy -Dusername=mani_uho -Dpassword=Manimani1 -Denc.key=abcdefgh123456789101112 -Danypoint.platform.client_id=8a70cdce412245e8b6d2abb963b43fd1 -Danypoint.platform.client_secret=3bEa4bb899d4452FB5E6C7987846a5b4'
      }
	  
	}
  }
}
