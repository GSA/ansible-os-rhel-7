pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        ansiblePlaybook(playbook: 'test.yml', colorized: true, inventory: 'local')
      }
    }
  }
}