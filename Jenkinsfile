pipeline {
  agent any
  stages {
    stage('Build') {
      agent {
        docker {
          image 'build:latest'
          args '-p 3000:3000'
        }

      }
      steps {
        sh '''sh "./mvnw package"
archive \'java -jar target/*.jar\''''
      }
    }
  }
}