pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        sh '''docker version

./mvnw package'''
      }
    }
    stage('Docker') {
      agent any
      steps {
        sh '''docker build -t pet-clinic .

docker tag pet-clinic nicolaskobelt/ingsoft3_final:latest

docker login -u=nicolaskobelt -p=Noworries19

docker push nicolaskobelt/ingsoft3_final:latest
'''
      }
    }
    stage('Test') {
      parallel {
        stage('Firefox') {
          steps {
            sh '''export PATH=/opt/apache-maven-3.5.4/bin:$PATH

mvn clean verify -Dbrowser=firefox -Dheadless=false'''
          }
        }
        stage('Chrome') {
          steps {
            sh '''export PATH=/opt/apache-maven-3.5.4/bin:$PATH

mvn clean verify -Dbrowser=Chrome -Dheadless=false'''
          }
        }
      }
    }
  }
}