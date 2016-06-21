stage 'Init'
node {
  checkout scm
  step([
    $class: 'GitHubCommitStatusSetter',
    contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'mystatus']
  ])
  sh 'echo $BRANCH_NAME'
}
if (env.BRANCH_NAME == 'master') {
  stage 'Only on master'
  println 'This happens only on master'
} else {
  stage 'Other branches'
  println "Current branch ${env.BRANCH_NAME}"
}
node {
step([
  $class: 'GitHubCommitStatusSetter',
  contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'mystatus']
])
}