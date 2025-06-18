pipeline {
	agent {
		docker {
			image "maven:3.6.3"
		}
	}

	stages {
		stage('Build') {
			steps {
				sh "maven --version"
				echo "Build"
			}
		}
		stage('Test') {
			steps {
				echo "Test"
			}
		}
		stage('anotherTest') {
			steps {
				echo "anotherTest"
			}
		}
	}
	
	post {
		always {
			echo "this runs always"
		}
		success {
			echo "printing on success"
		}
		failure {
			echo "printing on failure"
		}
	}
}
