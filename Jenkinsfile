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
                sh 'ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook playbook.yml'
            }    
        }    
    }
}
