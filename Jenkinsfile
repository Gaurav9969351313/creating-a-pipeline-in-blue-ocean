pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'node:6-alpine'
    }

  }
  stages {
    stage('Starting') {
      steps {
        echo 'Installation Started'
      }
    }
    stage('Install Deps') {
      steps {
        sh 'npm install'
      }
    }
    stage('Test') {
      environment {
        CI = 'true'
      }
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }
  }
}