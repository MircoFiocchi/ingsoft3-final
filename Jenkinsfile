pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        sh './mvnw package'
      }
    }
    stage('Test') {
      environment {
        CI = 'true'
      }
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }
  }
}