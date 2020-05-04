// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// 	stage('Integration Test') {
// 		echo "IntegrationTest"
// 	}
// }

pipeline {
	// agent any
	agent { 
		docker{
			image "maven:3.6.3"
		}
	}
	stages{
		stage('Build') {
			steps {
				sh 'mvn --version'
				echo "Build"
				}
		}
		stage('Test') {
			steps {
				echo "Test"
			}
		}
		stage('Integration Test') {
			steps {
				echo "IntegrationTest"
			}
		}
	}
	post{
		always{
			echo "Script always run"

		}
		success{
			echo "Build is always a sucess"

		}
		failure{
			echo "Build Fails"
		}
	}
}