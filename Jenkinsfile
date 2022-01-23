pipeline {
    agent any

    stages {
        stage('Vaidation') {
            steps {
              echo 'Validate Project..'
		      sh 'mvn validate'
		      sh 'mvn compile'
            }
        }
        stage('UnitTest') {
            steps {
              echo 'Testing..'
		      sh 'mvn test'
            }
        }
        stage('SonarAnalysis') {
            steps {
              echo 'Sonar Analysis....'
		      sh 'mvn sonar:sonar \
  -Dsonar.host.url=http://65.1.106.126:9000 \
  -Dsonar.login=c933f329af1e8eb72d431d40358d465abbdc2a3b'
            }
		
        }
	
	    stage('Deploy') {
            steps {
              echo 'Deploy....'
		      sh 'mvn deploy'
            }
		
        }
	
	 
	
		
       
    }
}
