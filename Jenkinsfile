pipeline {
	agent {
		docker {
			image "node:24-alpine3.21"
		}
	}

	stages {
		stage('Build') {
			steps {
				sh "node --version"
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
