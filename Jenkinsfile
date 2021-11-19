pipeline {
agent any
      environment {
   MY_CRED = credentials('anypointPlatform')
   MY_KEY = credentials('Denc.key')
   MY_CLIENT = credentials('Danypoint.platform.client_id')
   MY_SECRET = credentials('Danypoint.platform.client_secret')             
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
      bat 'mvn clean package deploy -DmuleDeploy -Pdev -Dusername=$MY_CRED_USR -Dpassword=$MY_CRED_PSW -Denc.key=$MY_KEY -Danypoint.platform.client_id=$MY_CLIENT -Danypoint.platform.client_secret=$MY_SECRET'
    }
  }
}

}
