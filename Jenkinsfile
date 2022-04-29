pipeline {
     agent any
    
    parameters {
         choice choices: ['qa', 'production'], description: 'Select environment for deployment', name: 'DEPLOY_TO'
       }

          stage('Deliver') {
            steps {
              sshagent(['vagrant']) {
                  sh 'ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook -i ${DEPLOY_TO}.ini playbook.yml'
              }
            }
        }
      
    }
}
