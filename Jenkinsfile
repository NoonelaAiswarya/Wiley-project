pipeline {
  agent any
  stages {
    stage('Checkout code') {
      steps {
        git(url: 'https://github.com/NoonelaAiswarya/Wiley-project', branch: 'main')
      }
    }

    stage('Test') {
      steps {
        sh 'cd app && pip3 install -r requirements.txt'
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t aishyadav/mini-project01:latest .'
      }
    }

  }
}