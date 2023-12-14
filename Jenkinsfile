pipeline {
  agent any
  
  stages {
    stage('Deploy Role') {
      steps {
        script {
          // Install boto3 using pip
          #sh 'pip install boto3'
          
          // Disable host key checking for Ansible
          chmod 400 /home/ubuntu/tool/ansible_role/mykey.pem
          sh 'ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook playbook.yml'
        }
      }
    }
  }
}
