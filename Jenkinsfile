pipeline {
    agent any
    stages {
        stage ("SCM checkout") {
            steps {
                git "https://github.com/c-shantanu/ansible_role.git"
                
            }
        }
        stage(" execute Ansible") {
           steps {
                ansiblePlaybook credentialsId: 'mykey', disableHostKeyChecking: true, installation: 'Ansible', inventory: 'aws_ec2.yml', playbook: 'playbook.yml'
            }    
        }    
    }
}
