pipeline {
	agent any
	// agent {
	// 	docker {
	// 		image "node:24-alpine3.21"
	// 	}
	// }

	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
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
		stage('Compile') {
			steps {
				echo "mvn clean compile"
			}
		}
		// stage('Test') {
		// 	steps {
		// 		sh "mvn test"
		// 	}
		// }
		// stage('Integration test') {
		// 	steps {
		// 		echo "mvn failsafe:integration-test failsafe:verify"
		// 	}
		// }
		stage('Build docker image') {
			steps {
				sh "docker build currency-exchange:1.0"
				sh "docker run -d -p 8000:8000 currency-exchange:1.0"
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
