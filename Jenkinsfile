pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        sh './mvnw package'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo \'Deploying\''
      }
    }
  }
}