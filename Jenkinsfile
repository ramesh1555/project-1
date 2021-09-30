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
  -Dsonar.host.url=http://34.205.15.108:9000 \
  -Dsonar.login=81658bba0c085187900ffc8b8872b2fbd934ff5f'
            }
		
        }
	stage('run playbooks on ansible server') {
		def dockerrun = 'ansible-playbook cal.yml'
		sshagent(['ansible_docker']) {
			sh "ssh -o StrictHostKeyChecking=no centos@172.31.27.37 ${dockerrun}"
            }
	    } 
    }
}
