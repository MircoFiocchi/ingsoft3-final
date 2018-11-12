pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        sh './mvnw package'
        sh 'npm install'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo \'Deploying\''
      }
    }
  }
}