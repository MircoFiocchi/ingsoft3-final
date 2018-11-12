pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
      }
    }
    stage('Deploy'){
      steps {
         echo 'Deploying'
      }
    }
  }
}
