pipeline {
    agent any

    environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/c-shantanu/ansible_role.git'
            }
        }
        
        
        stage('Prometehus Deploy') {
            steps {
                // Deploy Prometheus
                sh ''' cd /var/lib/jenkins/workspace/ansible_role/
                ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook playbook.yml    '''
         
            }
        }
    }
}
