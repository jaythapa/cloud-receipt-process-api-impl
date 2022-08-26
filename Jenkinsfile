pipeline {

	agent any
	
	tools {
        maven 'maven 3.8.6'
        jdk 'jdk8'
    }
    
	environment {
    	ANYPOINT_CREDENTIAL = credentials('anypoint.credential') 
    }
	
	stages {
	
		stage ("Build") {
			
			steps {
			    echo 'Build Phase in progress'
				bat 'mvn -B -DskipTests clean install'
			}
		}
		
		stage ("Test") {
		
			steps{
			  echo 'Testing Phase in Progress'
			  
			}
			
		}
		
		stage ('Deploy CloudHub') {
			steps {
				script {		   
		   	  		echo 'Deploying mule project'		   
		   	  		bat 'mvn deploy -DmuleDeploy -Dmule.version=4.4.0 -Dusername=%ANYPOINT_CREDENTIAL_USR% -Dpassword=%ANYPOINT_CREDENTIAL_PSW%  -DworkerType=micro  -Dregion=us-west-2'		   	  
		    	}		      
		   }
		}
	}
}
		
		
	
	
			