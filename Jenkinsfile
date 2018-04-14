pipeline {
  agent none
  stages {
    stage('test') {
      parallel {
        stage('test') {
          steps {
            timestamps()
          }
        }
        stage('ste1 get code') {
          steps {
            echo 'getting code'
          }
        }
        stage('stage2 compile code') {
          steps {
            timestamps() {
              echo 'hi'
            }
            
          }
        }
        stage('jaunt done here') {
          steps {
            sh 'echo"hello"'
          }
        }
      }
    }
    stage('dev') {
      steps {
        timestamps()
      }
    }
    stage('unit1') {
      parallel {
        stage('test') {
          steps {
            sh 'echo"test\\"'
          }
        }
        stage('unit_unit1 here') {
          steps {
            sh 'echo"unit"'
          }
        }
      }
    }
    stage('prod') {
      steps {
        echo 'hello '
      }
    }
  }
}