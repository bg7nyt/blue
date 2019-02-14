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
            archiveArtifacts(fingerprint: true, onlyIfSuccessful: true, artifacts: 'READMD.md', excludes: 'doc.md')
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