pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build java 7') {
          agent any
          steps {
            echo 'Success!'
            stash(name: 'Stash build 7', allowEmpty: true, includes: 'target/**')
          }
        }
        stage('build java 8') {
          agent any
          steps {
            echo 'parallel build'
            echo 'I am $BUZZ_NAME'
          }
        }
      }
    }
    stage('test') {
      parallel {
        stage('testing A') {
          steps {
            echo 'Another message'
            unstash 'Stash build 7'
          }
        }
        stage('testing B') {
          agent any
          steps {
            echo 'testing parallel'
          }
        }
      }
    }
  }
  environment {
    BUZZ_NAME = 'govind'
  }
}