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
        stage('test1') {
          steps {
            sleep 1
          }
        }
        stage('test2') {
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