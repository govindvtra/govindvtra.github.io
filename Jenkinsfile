pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sleep 20
            echo 'Success!'
            archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true, allowEmptyArchive: true)
          }
        }
        stage('build 2') {
          steps {
            echo 'parallel build'
          }
        }
      }
    }
    stage('test') {
      steps {
        echo 'Another message'
        junit(testResults: '**/surefire-reports/**/*.xml', allowEmptyResults: true)
      }
    }
  }
  environment {
    BUZZ_NAME = 'govind'
  }
}