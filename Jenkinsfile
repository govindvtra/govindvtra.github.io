pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sleep 20
        echo 'Success!'
        archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true, allowEmptyArchive: true)
      }
    }
    stage('test') {
      steps {
        echo 'Another message'
        junit '**/surefire-reports/**/*.xml'
      }
    }
  }
}