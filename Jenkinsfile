pipeline {
	agent any
  // agent { docker { image 'maven:3.6.3' } }
  // agent { docker { image 'node:22' } }
  environment {
    dockerHome = tool 'my-docker'
    mavenHome = tool 'my-maven'
    PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
  }
	stages {
		stage ('Checkout') {
			steps {
        sh 'mvn --version'
        sh 'docker version'
				echo "Build"
        echo "$PATH"
        echo "BUILD_NUMBER: $env.BUILD_NUMBER"
        echo "BUILD_ID: $env.BUILD_ID"
        echo "BUILD_TAG: $env.BUILD_TAG"
        echo "BUILD_URL: $env.BUILD_URL"
			}
		}

    stage ('Compile') {
      steps {
        sh 'mvn clean compile'
      }
    }

		stage ('Test') {
			steps {
				sh 'mvn test'
			}
		}

		stage ('Integration Test') {
			steps {
				sh 'mvn failsafe:integration-test failsafe:verify'
			}
		}
	}
  post {
    always {
      echo 'I am awesome. I run always.'
    }

    success {
      echo 'I run with success.'
    }

    failure {
      echo 'I run with failure.'
    }
  }
}
