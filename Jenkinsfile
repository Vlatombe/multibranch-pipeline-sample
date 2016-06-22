stage 'Init'
node {
  checkout scm
  sh 'git rev-parse HEAD>GIT_COMMIT'
  sha1 = readFile 'GIT_COMMIT'
  step([
    $class: 'GitHubCommitStatusSetter',
    commitShaSource: [$class: 'ManuallyEnteredShaSource', sha: sha1], 
    contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'mystatus']
  ])
  sh 'echo $BRANCH_NAME'
  step([
    $class: 'GitHubCommitStatusSetter',
    commitShaSource: [$class: 'ManuallyEnteredShaSource', sha: sha1], 
    contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'mystatus']
  ])
}