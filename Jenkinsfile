pipeline {
    agent any
    environment {
 	     PATH = "/opt/maven/bin:$PATH"
    }
    stages {
     	stage("build") {
	        steps {
		        sh 'mvn clean deploy'
	        }
	    }
	    stage("SonarQube analysis") {
	   		environment {
				scannerHome = tool 'sonarqube-scanner'	
	   		}
	  		 steps {
	       		withSonarQubeEnv('sonarqube-sri') {
		   			sh "${scannerHome}/bin/sonar-scanner"
				}
	  		 }
		}
	}
}

	
     
