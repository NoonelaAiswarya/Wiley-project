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
        sh 'cd app && pip3 install -r requirements.txt && pip3 install nose && nosetests --with-xunit'
      }
    }

  }
}