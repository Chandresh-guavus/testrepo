pipeline {
  agent any
  job('upstreamJob') {
    scm {
        git {
            remote {
                github('Chandresh-guavus/testrepo.git')
                refspec('+refs/pull/*:refs/remotes/origin/pr/*')
            }
            branch('${sha1}')
        }
    }

    triggers {
        githubPullRequest {
            orgWhitelist('Guavus'
            cron('* * * * *')
            triggerPhrase('special trigger phrase')
            onlyTriggerPhrase()
            useGitHubHooks()
            permitAll()
            autoCloseFailedPullRequests()
            displayBuildErrorsOnDownstreamBuilds()
            whiteListTargetBranches(['master','test', 'test2'])
            allowMembersOfWhitelistedOrgsAsAdmin()
            extensions {
                commitStatus {
                    context('deploy to staging site')
                    triggeredStatus('starting deployment to staging site...')
                    startedStatus('deploying to staging site...')
                    addTestResults(true)
                    statusUrl('http://mystatussite.com/prs')
                    completedStatus('SUCCESS', 'All is well')
                    completedStatus('FAILURE', 'Something went wrong. Investigate!')
                    completedStatus('PENDING', 'still in progress...')
                    completedStatus('ERROR', 'Something went really wrong. Investigate!')
                }
                buildStatus {
                    completedStatus('SUCCESS', 'There were no errors, go have a cup of coffee...')
                    completedStatus('FAILURE', 'There were errors, for info, please see...')
                    completedStatus('ERROR', 'There was an error in the infrastructure, please contact...')
                }
            }
        }
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
