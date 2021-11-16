pipeline {

  agent any

  stages {
    stage('Build') {
      steps {
            bat 'mvn clean install'
      } 
    }

    stage('Test') {
      steps {
          bat "mvn test"
      }
    }

     stage('Deployment') {
      environment {
        ENVIRONMENT = 'dev'
        APP_NAME = '<DEV-API-NAME>'
      }
      steps {
            bat 'mvn clean package deploy -Pdev -DmuleDeploy -Dusername=mani_uho -Dpassword=Manimani1 -Denc.key=qwerty987654321 -Danypoint.platform.client_id=b5380b80479645308fa3c1853e314501 -Danypoint.platform.client_secret=248844e0C9124EAfa4eE6ceAE070d752 '
      }
    }

  }

}