pipeline {
  agent any
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
      environment {
        ANYPOINT_CREDENTIALS = credentials('anypointPlatform')
	      
      }
      steps {
        bat 'mvn clean package deploy -DmuleDeploy -Pdev -Denc.key=qwerty987654321 -Danypoint.platform.client_id=b5380b80479645308fa3c1853e314501 -Danypoint.platform.client_secret=248844e0C9124EAfa4eE6ceAE070d752'
      }
    }
  }
}
