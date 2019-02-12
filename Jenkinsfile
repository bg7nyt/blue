pipeline {
  agent any
  stages {
    stage('Version') {
      steps {
        sh 'mvn -version'
      }
    }
  }
  environment {
    name = 'neo'
  }
}