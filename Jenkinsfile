pipeline {
  agent any
	triggers {
			githubPullRequest {
				cron("*/2 * * * *")
				permitAll(false)
				triggerPhrase("ok to test")
			}
		}


  stages {
    stage('test') {
      steps {
        sh 'echo "success"'
      }
    }
  }
}
