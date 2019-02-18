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
        stage('dir') {
          steps {
            dir(path: 'src') {
              error 'aaa'
            }

          }
        }
        stage('subduer') {
          steps {
            dir(path: '/src') {
              echo 'begin'
              sh '''mvn test
'''
              echo 'end'
            }

          }
        }
        stage('alocate') {
          steps {
            ws(dir: 'src') {
              ws(dir: 'aaa') {
                echo 'aaa'
              }

            }

          }
        }
        stage('node') {
          steps {
            node(label: 'java-8') {
              sh 'mvn package'
            }

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
        stage('job') {
          steps {
            build(job: '11', wait: true, propagate: true, quietPeriod: 1)
          }
        }
      }
    }
  }
  environment {
    name = 'neo'
  }
}