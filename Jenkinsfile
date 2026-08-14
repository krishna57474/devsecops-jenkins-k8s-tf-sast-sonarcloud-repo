pipeline {
  agent any
  tools { 
        maven 'Maven_3_9_16'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
			mvn clean verify org.sonarsource.scanner.maven:sonar-maven-plugin:5.4.0.6343:sonar \
  -Dsonar.projectKey=devsecops-1011 \
  -Dsonar.organization=DevSecOps-1011 \
  -Dsonar.host.url=https://sonarcloud.io \
  -Dsonar.token="867d16b35eaccfe9bfd13369452871d586523706" \
  -e
			}
        } 
  }
}
