pipeline {
  agent any
  tools { 
        maven 'maven'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
				 sh '''
                    mvn clean verify \
                      org.sonarsource.scanner.maven:sonar-maven-plugin:5.4.0.6343:sonar \
                      -Dsonar.projectKey=krishna57474 \
                      -Dsonar.organization=krishna57474 \
                      -Dsonar.host.url=https://sonarcloud.io \
                      -Dsonar.token="5f2aff4b4de39cc78b32f96be1d0fbbdc5f43c2c" \
                      -e
                '''
			}
    }

	stage('RunSCAAnalysisUsingSnyk') {
            steps {		
				withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
					sh 'mvn snyk:test -fn'
				}
			}
    }		
  }
}
