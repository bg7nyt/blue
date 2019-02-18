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
        stage('bat') {
          steps {
            bat(returnStatus: true, returnStdout: true, label: 'aa', encoding: 'utf-8', script: 'dir')
          }
        }
        stage('Git') {
          steps {
            git(url: 'http://github.com/test/test.git', branch: 'master', changelog: true, credentialsId: '123', poll: true)
          }
        }
        stage('exists') {
          steps {
            fileExists '/sss'
          }
        }
      }
    }
  }
  environment {
    name = 'neo'
  }
}