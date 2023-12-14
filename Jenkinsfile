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
    stage('Deploy Role') {
      steps {
        script {
          // Make sure to use the correct path to the key file
          chmod 400 '/home/ubuntu/tool/ansible_role/mykey.pem'
          
          // Add the full path to the playbook.yml file
          sh 'ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook /home/ubuntu/tool/ansible_role/playbook.yml'
        }
      }
    }
  }
}
