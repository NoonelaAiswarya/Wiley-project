pipeline {
  agent any
  stages {
    stage('Code checkout') {
      steps {
        git(url: 'https://github.com/NoonelaAiswarya/Wiley-project', branch: 'docker')
      }
    }
    stage('Test') {
      steps {
        echo 'Starting unittests'
        sh 'pip3 install -r requirements.txt && pip3 install nose && nosetests --with-xunit'
      }
    }
    stage('Build') {
      steps {
        sh '''echo $USER
'''
        sh 'docker build -t aishyadav/miniproject01:latest .'
      }
    }
    stage('Deploy') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'dockerhubcredentials', usernameVariable: 'DOCKERHUB_USERNAME', passwordVariable: 'DOCKERHUB_PASSWORD')]) {
          sh 'docker login -u $DOCKERHUB_USERNAME -p $DOCKERHUB_PASSWORD'
          sh 'docker push aishyadav/miniproject01:latest'
        }
      }
    }
  }
}
