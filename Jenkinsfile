pipeline {
  agent any
  
  stages {
    stage('Deploy Role') {
      steps {
          sh 'ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook playbook.yml'
        }
      }
    }
  }
