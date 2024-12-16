pipeline {
  agent any
  stages {
    stage('Start') {
      steps {
        echo 'Starting a Pipeline to configured tomcat on the servers'
      }
    }

    stage('Tomcat Status') {
      agent {
        label 'test'
      }
      steps {
        sh 'bash /home/ec2-user/tomcatsetup.sh'
      }
    }

    stage('End') {
      steps {
        echo 'End'
      }
    }

  }
}