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
      parallel {
        stage('Firefox') {
          agent any
          steps {
            sh 'mvn clean verify -Dbrowser=firefox -Dheadless=false'
          }
        }
        stage('Chrome') {
          steps {
            sh 'mvn clean verify -Dbrowser=chrome -Dheadless=false'
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "deploy"'
      }
    }
  }
}