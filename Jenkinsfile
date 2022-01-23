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
  -Dsonar.login=31beba46dac1fd4dfce79dd4df2da8e7e08209d4'
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
