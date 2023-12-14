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
        stage('Grant Persmission') {
            steps {
                sh 'sudo chmod 400 /var/lib/jenkins/workspace/tool_role/mykey.pem'
            }
        }
        stage('Deploy Tool') {
            steps {
                sh 'cd /var/lib/jenkins/workspace/tool_role/'
                sh 'ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook playbook.yml'
            }
        }
    }
}
