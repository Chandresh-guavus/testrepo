@Library('jenkins_lib')_
pipeline {
agent any

    environment {
    // Define global environment variables in this section
    buildNum = currentBuild.getNumber()
    buildType = BRANCH_NAME.split('/').first()
    branchVersion = BRANCH_NAME.split('/').last()
    buildVersion = '1.0.0'
    stRepoPath= 'cdap-plugins'
    stFrameworkPath = "${env.stRepoPath}/automation"
  }


  stages {
    stage('test') {
      steps {
        sh 'echo "${env.branchVersion}"&& touch a.rpm'
        artifact_push("rpm",env.buildType)
      }
    }
  }
}
