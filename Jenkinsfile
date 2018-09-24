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
   
         
       }
  }
}
}
