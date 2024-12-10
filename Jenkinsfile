pipeline{
    agent any

    stages{
        stage("Starting"){
            steps{
                echo "========Starting pipeline to create a user========"
            }

        }

                stage("Invoking user create Playbook"){


            steps{

                echo "========Starting pipeline to create a user========"
parameters {
  string defaultValue: 'awez', name: 'user_name'
}
                ansiblePlaybook playbook: '/home/ec2-user/ansible/usercreation.yml', vaultTmpPath: ''
            }

        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
