pipeline {
  agent any
  stages {
    stage('write') {
      parallel {
        stage('write') {
          steps {
            writeFile(file: 'hello.txt', text: 'Helloworld')
          }
        }
        stage('read') {
          steps {
            readFile 'hello.txt'
          }
        }
      }
    }
  }
}