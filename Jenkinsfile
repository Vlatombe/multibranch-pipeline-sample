node {
  step([$class: 'GitHubSetCommitStatusBuilder'])
  stage('checkout') {
    checkout scm
  }
  stage('build') {
    sh 'git rev-parse HEAD>GIT_COMMIT'
    sha1 = readFile 'GIT_COMMIT'
    
    sh 'echo $BRANCH_NAME'
    currentBuild.result = 'SUCCESS'
    step([$class: 'GitHubCommitStatusSetter'])
  }
}