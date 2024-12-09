pipeline {
  agent any
  stages {
    stage('Display Message') {
      agent any
      steps {
        echo 'Starting a playbook to create user on the server'
      }
    }

    stage('Create a user') {
      steps {
        ansiblePlaybook(playbook: '/home/ec2-user/ansible', becomeUser: 'root', disableHostKeyChecking: true)
      }
    }

  }
}