pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        ansiblePlaybook(playbook: 'tasks/main.yml', colorized: true)
      }
    }
  }
}