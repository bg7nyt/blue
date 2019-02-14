pipeline {
  agent any
  stages {
    stage('Version') {
      parallel {
        stage('Version') {
          steps {
            sh 'mvn -version'
          }
        }
        stage('test') {
          steps {
            archiveArtifacts 'README.md'
          }
        }
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