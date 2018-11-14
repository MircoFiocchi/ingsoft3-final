pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        sh '''docker version

./mvnw package

mvn clean verify -Dbrowser=firefox -Dheadless=false'''
      }
    }
    stage('Docker') {
      agent any
      steps {
        sh '''docker build -t pet-clinic .

docker tag pet-clinic nicolaskobelt/ingsoft3_final:latest

docker login -u=nicolaskobelt -p=Noworries19

docker push nicolaskobelt/ingsoft3_final:latest'''
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "deploy"'
      }
    }
  }
}