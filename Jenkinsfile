pipeline {
    agent any
    
    tools {
        maven 'apache-maven-3.6.3' 
    }
    
    stages {
    	 
	   stage ('Clone') {
            steps {
                git branch: 'master', url: "https://gitlab.com/mromdhani/07-jenkins-maven-plugin-02-static-code-analysis-sonarqube.git"
            }
	    }
	 
	  stage('Static Code Analysis'){
		  steps {
    		bat "mvn clean verify sonar:sonar -Dsonar.projectName=07-static-code-analysis-sonarqube -Dsonar.projectKey=07-static-code-analysis-sonarqube -Dsonar.projectVersion=$BUILD_NUMBER";
		  }
	  }
    }
  }