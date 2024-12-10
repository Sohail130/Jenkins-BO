pipeline{
    agent any
parameters {
     string(
            defaultValue: 'awez',
            description: 'Enter the username to create',
            name: 'user_name'
        )
}
    stages{
        stage("Starting"){
            steps{
                echo "========Starting pipeline to create a user========"
            }

        }
                stage("Invoking user create Playbook"){


            steps{

                echo "========Starting pipeline to create a user========"
                script {
                    def username = params.user_name
                    sh """
                        ansible-playbook /home/ec2-user/ansible/usercreation.yml -e "user_name=${username}"
                    """    
             #   ansiblePlaybook (
              #      playbook: '/home/ec2-user/ansible/usercreation.yml', 
               #     vaultTmpPath: '', 
                #    extraVars: [user_name: "${params.user_name}"]
                 #   )
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
