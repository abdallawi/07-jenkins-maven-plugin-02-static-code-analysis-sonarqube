pipeline {
    agent any
    
    tools {
        maven 'my-maven-3' 
    }
    
    stages {
    	 
	   stage ('Clone') {
            steps {
                git branch: 'master', url: "https://github.com/abdallawi/07-jenkins-maven-plugin-02-static-code-analysis-sonarqube.git"
            }
	    }
	 
	  stage('Static Code Analysis '){
		  steps {
    		sh "mvn clean verify sonar:sonar -Dsonar.host.url=http://host.docker:9000  -Dsonar.projectName=07-static-code-analysis-sonarqube -Dsonar.projectKey=07-static-code-analysis-sonarqube -Dsonar.projectVersion=$BUILD_NUMBER";
		  }
	  }
    }
  }