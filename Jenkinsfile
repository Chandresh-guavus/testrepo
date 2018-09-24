pipeline {
  agent any
	triggers {
	        issueCommentTrigger('.*test this please.*')
	    }


  stages {
    stage('test') {
      steps {
        sh 'echo "success"'
      }
    }
	   post {
       always {
   
            pullRequest.createStatus(
                         context: 'continuous-integration/jenkins/pr-merge/tests',
                         description: 'All tests are passing',
                         targetUrl: "${env.JOB_URL}/testResults")
       }
  }
}
