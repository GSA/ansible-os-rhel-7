pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''yum install curl

\\curl -sSL https://get.rvm.io | bash -s stable --ruby

gem install bundler

bundle install

bundle exec kitchen test test-centos-7'''
      }
    }
  }
}