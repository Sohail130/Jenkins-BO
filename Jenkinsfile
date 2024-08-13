pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''pwd
date'''
      }
    }

    stage('test') {
      parallel {
        stage('test') {
          steps {
            echo 'test stage'
          }
        }

        stage('test1') {
          steps {
            echo 'test1 mess'
          }
        }

      }
    }

    stage('deploy') {
      steps {
        echo 'deploy'
        sleep 13
      }
    }

  }
}