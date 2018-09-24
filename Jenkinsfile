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
 pullRequest.comment('This PR is OK to MERGE')
    }
    failure {
 pullRequest.comment('This PR is NOT FIT to MERGE')    }
  }
}
