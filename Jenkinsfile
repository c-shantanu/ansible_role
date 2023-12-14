pipeline {
  agent any
  
  stages {
    stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/c-shantanu/ansible_role.git'
            }
    stage('Deploy Role') {
      steps {
          chmod 400 /home/ubuntu/tool/ansible_role/mykey.pem
          sh 'ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook playbook.yml'
        }
      }
    }
  }
}
