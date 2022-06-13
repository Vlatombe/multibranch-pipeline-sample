stage('Init') {
  node {
    checkout scm
    restoreDependenciesCache 'cache'
    sh 'echo $BRANCH_NAME'
    sh '''#!/bin/bash -eu
    if [ -f toto.txt ]; then
        echo 'toto.txt already exists'
    else
        date > toto.txt
        echo $BRANCH_NAME >> toto.txt
    fi
    cat toto.txt
    '''
    if (env.CHANGE_TARGET == null) {
      saveDependenciesCache(name: 'cache', includes: 'toto.txt')
    }
  }
  if (env.BRANCH_NAME == 'master') {
    stage('Only on master') {
      println 'This happens only on master'
    }
  } else {
    stage('Other branches') {
      println 'Current branch ' + env.BRANCH_NAME
    }
  }
}