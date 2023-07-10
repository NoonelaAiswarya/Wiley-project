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

    stage('Deploy') {
      steps {
        sh '''withCredentials([usernamePassword(credentialsId: \'dockerhubcredentials\', usernameVariable: \'DOCKERHUB_USERNAME\', passwordVariable: \'DOCKERHUB_PASSWORD\')]) 

{
  sh \'docker login -u $DOCKERHUB_USERNAME -p $DOCKERHUB_PASSWORD\';
  sh \'docker push aishyadav/mini-project01:latest\'
}
'''
      }
    }

  }
}