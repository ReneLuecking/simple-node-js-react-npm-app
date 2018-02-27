pipeline {
	agent {
		docker {
			image 'node:6-alpine'
			args '-p 3000:3000 -e HTTP_PROXY="http://wwwproxy.ser.net:8080" -e HTTPS_PROXY="http://wwwproxy.ser.net:8080"'
		}
	}
	environment {
		CI = 'true'
	}
	stages {
		stage('Build') {
			steps {
				sh 'npm install'
			}
		}
		stage('Test') {
			steps {
				sh './jenkins/scripts/test.sh'
			}
		}
	}
}
