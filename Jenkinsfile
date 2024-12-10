pipeline {
    agent any
    parameters {
        string(
            defaultValue: 'awez',
            description: 'Enter the username to create',
            name: 'user_name'
        )
    }

    environment {
        USER_NAME = "${params.user_name}"
    }

    stages {
        stage("Starting") {
            steps {
                echo "========Starting pipeline to create a user========"
            }
        }

        stage("Invoking user create Playbook") {
            steps {
                echo "========Starting pipeline to create a user========"
                ansiblePlaybook (
                    playbook: '/home/ec2-user/ansible/usercreation.yml',
                    vaultTmpPath: '',
                    extraVars: [user_name: "${env.USER_NAME}"]
                )
            }
        }
    }

    post {
        always {
            echo "========always========"
        }
        success {
            echo "========pipeline executed successfully ========"
        }
        failure {
            echo "========pipeline execution failed========"
        }
    }
}
