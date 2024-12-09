pipeline {
  agent any
  stages {
    stage('Display Message') {
      steps {
        echo 'Starting a playbook to create user on the server'
      }
    }

    stage('Create a user') {
      steps {
        ansiblePlaybook(playbook: '/home/ec2-user/ansible', become: true, becomeUser: 'root', checkMode: true, disableHostKeyChecking: true)
      }
    }

  }
}