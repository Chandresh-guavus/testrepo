@Library('jenkins_lib')_
pipeline {
agent {
    node {
        label 'slave'
        
    }
}

    environment {
    // Define global environment variables in this section
    buildNum = currentBuild.getNumber()
    buildType = BRANCH_NAME.split('/').first()
    branchVersion = BRANCH_NAME.split('/').last()
    buildVersion = '1.0.0'
    
    stRepoPath= 'cdap-plugins'
    stFrameworkPath = "${env.stRepoPath}/automation"
    //artifactoryServer = Artifactory.server('ggn-artifactory')
    VERSION = '1.0.0'
  }


  stages {
    stage('test') {
      steps {
        sh 'echo "${branchVersion}"&& mkdir dist && touch ./dist/a.rpm'
        script{
         rpm_push(env.buildType, 'dist', 'ggn-dev-rpms/test')   
        }
        }
      }
    }
  }
