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
            sh '''export PATH=/opt/apache-maven-3.5.4/bin:$PATH

mvn clean verify -Dbrowser=firefox -Dheadless=false'''
          }
        }
        stage('Chrome') {
          steps {
            sh '''export PATH=/opt/apache-maven-3.5.4/bin:$PATH

mvn clean verify -Dbrowser=chrome -Dheadless=false'''
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