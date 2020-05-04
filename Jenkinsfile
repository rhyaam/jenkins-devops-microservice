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
	agent any
	stages{
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
		sucess{
			echo "Build is always a sucess"

		}
		failure{
			echo "Build Fails"
		}
	}
}