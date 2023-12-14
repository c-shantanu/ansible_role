pipeline {
  agent any
  
  stages {
    stage('Deploy Role') {
      steps {
        script {
          // Install boto3 using pip
          sh 'pip install boto3'
          
          // Disable host key checking for Ansible
          sh 'ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook playbook.yml'
        }
      }
    }
  }
}
