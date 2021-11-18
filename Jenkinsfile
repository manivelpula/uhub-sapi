pipeline{
 agent any
 environment {
    ANYPOINT = credentials('anypointPlatform')
 }
 stages {
 	stage ('Build'){
 		steps {
 			withMaven(maven:'my-maven'){
 				bat 'mvn -f uhub-sapi/pom.xml clean install'
 			}
 		}
 	}
 	stage ('Deploy'){
 		steps {
 			withMaven(maven:'my-maven'){
 				
 			bat 'mvn -f uhub-sapi/pom.xml package deploy -DmuleDeploy -Dusername=${ANYPOINT_CREDENTIALS_USR} Dpassword=${ANYPOINT_CREDENTIALS_PSW} -Denc.key=${Denc.key} -Danypoint.platform.client_id=${Danypoint.platform.client_id} -Danypoint.platform.client_secret=${Danypoint.platform.client_secret} -Denvironment=Dev'
			}
 		}
 	}
 }

}
