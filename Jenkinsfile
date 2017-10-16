stage 'Init'
node {
  checkout scm
  sh 'echo $BRANCH_NAME'
}
if (env.BRANCH_NAME == 'master') {
  stage 'Only on master'
  println 'This happens only on master'
} else {
  stage 'Other branches'
  println "Current branch ${env.BRANCH_NAME}"
   println "Current build number ${env.BUILD_NUMBER}"
   println "build cause ${env.BUILD_CAUSE}"
   println "JOB_NAME ${env.JOB_NAME}"
   println "BUILD_TAG ${env.BUILD_TAG}"
   println "BUILD_URL  ${env.BUILD_URL }"
   println "JENKINS_URL ${env.JENKINS_URL}"
}

