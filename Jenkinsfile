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
        githubNotify account: '', context: '', credentialsId: 'github', description: '', gitApiUrl: '', repo: '', sha: '', status: 'SUCCESS', targetUrl: ''

    }
    githubNotify account: '', context: '', credentialsId: 'github', description: '', gitApiUrl: '', repo: '', sha: '', status: 'FAILURE', targetUrl: ''
("Build failed", "FAILURE");
    }
  }
}
