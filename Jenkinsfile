pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
        sh 'java -jar target/*.jar --httpPort=8282'
      }
    }
  }
}