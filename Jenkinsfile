pipeline {
	agent any
	// agent {
	// 	docker {
	// 		image "node:24-alpine3.21"
	// 	}
	// }

	environment {
		dockerHome = tools 'myDocker'
		mavenHome = tools 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}

	stages {
		stage('Build') {
			steps {
				// sh "node --version"
				echo "Build"
				echo "BranchName - $env.BRANCH_NAME"
				echo "path - $PATH"
				sh "docker version"
				sh "mvn --version"
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
		// stage('sendmail') {
		// 	steps {	
		// 		mail bcc: '', body: 'deployed successfully', cc: '', from: '', replyTo: '', subject: 'deployed', to: 'kanoj2108@gmail.com'
		// 	}
		// }
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
