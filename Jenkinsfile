pipeline {
	agent any

	stages {
		stage('Build') {
			steps {
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
