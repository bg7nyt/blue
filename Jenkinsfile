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
      parallel {
        stage('test') {
          steps {
            echo 'hello'
          }
        }
        stage('') {
          steps {
            sleep 1
          }
        }
        stage('') {
          steps {
            retry(count: 5) {
              echo 'hello'
            }

          }
        }
      }
    }
  }
  environment {
    name = 'neo'
  }
}