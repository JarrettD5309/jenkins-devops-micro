pipeline {
	// agent any
  // agent { docker { image 'maven:3.6.3' } }
  agent { docker { image 'node:22' } }
	stages {
		stage ('Build') {
			steps {
        // sh 'mvn --version'
        sh 'node --version'
				echo "Build"
			}
		}

		stage ('Test') {
			steps {
				echo "Test"
			}
		}

		stage ('Integration Test') {
			steps {
				echo "Integration Test"
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
