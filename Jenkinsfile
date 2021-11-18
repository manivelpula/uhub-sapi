pipeline{
 agent any
//  environment {
//     ANYPOINT = credentials('anypointPlatform')
//  } 
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
 				
 			bat 'mvn -f uhub-sapi/pom.xml package deploy -Pdev -DmuleDeploy -Dusername=mani_uho -Dpassword=Manimani1 -Denc.key=qwerty987654321 -Danypoint.platform.client_id=b5380b80479645308fa3c1853e314501 -Danypoint.platform.client_secret=248844e0C9124EAfa4eE6ceAE070d752 '
			}
 		}
 	}
 }

}
