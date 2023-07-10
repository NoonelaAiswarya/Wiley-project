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
        sh 'docker build -t aishyadav/mini-project01:latest /var/lib/jenkins/workspace/Wiley-project_main/app'
      }
    }

    stage('Log in to Dockerhub') {
      environment {
        DOCKERHUB_USER = 'aishyadav'
        DOCKERHUB_PASSWORD = 'PEM0175924'
      }
      steps {
        sh 'docker login  -u $DOCKERHUB_USER -p $DOCKERHUB_PASSWORD'
      }
    }

  }
}