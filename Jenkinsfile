pipeline {
  agent any
	
  stages {
    stage('test') {
      steps {
        sh 'echo "success"'
      }
    }
	 
  }
	post {
		success {
def comment = pullRequest.comment('This PR is OK to MERGE')
    }
    failure {
def comment = pullRequest.comment('This PR is NOT fit to MERGE')    }
  }
}
