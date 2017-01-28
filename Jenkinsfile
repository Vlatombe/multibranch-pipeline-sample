node {
  step([$class: 'GitHubSetCommitStatusBuilder', reposSource: [$class: 'ManuallyEnteredRepositorySource', url: 'https://github.com/Vlatombe/multibranch-pipeline-sample']])
  stage('checkout') {
    checkout scm
  }
  stage('build') {
    sh 'git rev-parse HEAD>GIT_COMMIT'
    sha1 = readFile 'GIT_COMMIT'
    
    sh 'echo $BRANCH_NAME'
    currentBuild.result = 'SUCCESS'
    step([$class: 'GitHubCommitStatusSetter', reposSource: [$class: 'ManuallyEnteredRepositorySource', url: 'https://github.com/Vlatombe/multibranch-pipeline-sample']])
  }
}