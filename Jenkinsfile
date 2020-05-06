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

	// agent { docker { image "maven:3.6.3" } }
	// agent { docker { image 'node:13.8' }	}

	environment{
	dockerHome = tool 'myDocker'
	mavenHome = tool 'myMaven'
	PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}

	stages{
		stage('Checkout') {
			steps {
				sh 'mvn --version'
				// sh 'node --version'
				sh 'docker version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "BUILD_TAG - $env.TAG"
				echo "BUILD_URL - $env.BUILD_URL"
				}
		}

		stage('Compile') {
			steps {
				sh "mvn clean compile" 
			}
		}

		stage ('Test') {
			steps {
				sh "mvn test" 
			}
		}

		stage ('Integration Test') {
			steps {
			 	sh "mvn failsafe:integration-test failsafe:verify"
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