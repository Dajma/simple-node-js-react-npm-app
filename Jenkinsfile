pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'npm install'
            sh 'npm audit fix'
          }
        }

        stage('Test') {
          steps {
            sh './jenkins/scripts/test.sh'
          }
        }

      }
    }

  }
  environment {
    CI = 'true'
  }
}