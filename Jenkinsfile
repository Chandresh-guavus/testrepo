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
        setBuildStatus("Build succeeded", "SUCCESS");
    }
    failure {
        setBuildStatus("Build failed", "FAILURE");
    }
  }
}
