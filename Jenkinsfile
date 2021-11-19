pipeline {
agent any
    environment {

   MY_CRED = credentials('anypointPlatform')

    }
stages {
  stage('Build') {
    steps {
      echo 'Application is in Building Phase'
      bat 'mvn clean install'
    }
  }

  stage('Test') {
    steps {
      echo 'Application is in Testing Phase'
      bat 'mvn test'
    }

  }
 
  stage('Deploy to Cloudhub') { 
  steps {

      bat 'mvn clean package deploy -DmuleDeploy -Pdev -Dusername=$MY_CRED_USR -Dpassword=$MY_CRED_PSW -Denc.key=${Denc.key} -Danypoint.platform.client_id=${Danypoint.platform.client_id} -Danypoint.platform.client_secret=${Danypoint.platform.client_secret}'

    }
  } 
        
      }

   

  }





