pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build java 7') {
          agent any
          steps {
            sleep 2
            echo 'Success!'
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