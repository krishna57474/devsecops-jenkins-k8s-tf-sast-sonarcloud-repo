pipeline {
  agent any
  tools { 
        maven 'Maven_3_9_16'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=devsecops-1011 -Dsonar.organization=DevSecOps-1011 -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=867d16b35eaccfe9bfd13369452871d586523706'
			}
        } 
  }
}
