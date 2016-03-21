stage 'Init'
node {
  checkout scm
  sh 'env'
  sh 'git rev-parse --abbrev-ref HEAD'
}
println scm
println env