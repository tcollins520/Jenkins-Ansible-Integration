pipeline {    
    agent any    

    stages {    

          stage('Checkout') {
            steps {
                dir('AnsibleDemo') {
                    git branch: 'main', url: 'https://github.com/tcollins520/Jenkins-Ansible-Integration.git'
                }
            }
        }

        stage('Execute playbook') {           
            steps {          
                ansiblePlaybook(
                    credentialsId: 'JenkinsAnsible',
                    disableHostKeyChecking: false,
                    installation: 'AnsibleDemo',
                    inventory: '/var/lib/jenkins/workspace/Jenkins-Ansible-Int/AnsibleDemo/inventory.yaml',
                    playbook: '/var/lib/jenkins/workspace/Jenkins-Ansible-Int/AnsibleDemo/install_nginx_PB.yml',
                    vaultTmpPath: ''
                )
            }
        }    
    }
}
