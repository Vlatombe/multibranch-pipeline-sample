stage 'Init'
node {
  checkout scm
  step([
    $class: 'GitHubCommitStatusSetter',
    contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'mystatus']
  ])
  sh 'echo $BRANCH_NAME'
  step([
    $class: 'GitHubCommitStatusSetter',
    contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'mystatus']
  ])
}