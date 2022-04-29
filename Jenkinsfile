pipeline {
     agent any
    
    parameters {
         choice choices: ['qa', 'production', 'cloud'], description: 'Select environment for deployment', name: 'DEPLOY_TO'
       }

    stages {
        stage('Build') {
            steps {
                sh 'ruby main.rb'
            }
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
