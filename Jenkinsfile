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
  -Dsonar.host.url=http://54.196.189.200:9000 \
  -Dsonar.login=81658bba0c085187900ffc8b8872b2fbd934ff5f'
            }
		
        }
	
    }
}
