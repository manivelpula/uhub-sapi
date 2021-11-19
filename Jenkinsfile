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


      bat 'mvn clean package deploy -DmuleDeploy -Pdev -Dusername=${anypointPlatform} -Dpassword=${anypointPlatform} -Denc.key=${Denc.key} -Danypoint.platform.client_id=${Danypoint.platform.client_id} -Danypoint.platform.client_secret=${Danypoint.platform.client_secret}'


    }


  }


}


}
