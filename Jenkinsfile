stage 'Init'
node {
  step([$class: 'GitHubSetCommitStatusBuilder'])
  checkout scm
  sh 'git rev-parse HEAD>GIT_COMMIT'
  sha1 = readFile 'GIT_COMMIT'
  
  sh 'echo $BRANCH_NAME'
  step([
    $class: 'GitHubCommitStatusSetter',
    statusResultSource: [
      $class: 'ConditionalStatusResultSource',
      results: [[
        $class: 'AnyBuildResult',
        message: 'Build is successful',
        state: 'SUCCESS'
      ]]
    ]
  ])
}