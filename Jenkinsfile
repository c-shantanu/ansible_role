pipeline {
  agent any
  
  stages {
    stage('Deploy Role') {
      steps {
        sh 'sudo apt-get install python-boto3 -S'
        sh 'ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook playbook.yml'
      }
    }
  }
}
