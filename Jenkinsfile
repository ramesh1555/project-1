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
  -Dsonar.host.url=http://44.195.66.135:9000 \
  -Dsonar.login=c933f329af1e8eb72d431d40358d465abbdc2a3b'
            }
		
        }
	
	    stage('Deploy') {
            steps {
              echo 'Deploy....'
		      sh 'mvn deploy'
            }
		
        }
	
	 
	    stage('ansible_docker') {
	
            sshagent(['ansible_docker']) {
		      echo 'reomte....'
		      sh 'ssh -o StrictHostKeyChecking=no centos@172.31.27.37 mkdir ram'
    
            }
        }
		
       
    }
}
