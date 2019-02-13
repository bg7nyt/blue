pipeline {
  agent any
  stages {
    stage('Version') {
      steps {
        sh 'mvn -version'
      }
    }
    stage('test') {
      steps {
        echo 'hello'
      }
    }
  }
  environment {
    name = 'neo'
  }
}