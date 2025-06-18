pipeline {
	agent any

	stages {
		stage('Build') {
			echo "Build"
		}
		stage('Test') {
			echo "Test"
		}
		stage('anotherTest') {
			echo "anotherTest"
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
