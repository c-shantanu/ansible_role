pipeline {
  agent any
  
  stages {
    stage('Deploy Role') {
      steps {
        sh 'apt-get install python-boto3'
        sh 'ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook playbook.yml'
      }
    }
  }
}
