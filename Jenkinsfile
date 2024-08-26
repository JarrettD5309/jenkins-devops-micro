pipeline {
	agent any
	stages {
		stage ('Build') {
			steps {
				echo "Integration Test"
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
	}	post {
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
