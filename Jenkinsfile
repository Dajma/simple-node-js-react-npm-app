pipeline {
  agent any
  stages {
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

    stage('Deliver') {
      steps {
        sh '''sh \'./jenkins/scripts/deliver.sh\'
sh \'./jenkins/scripts/kill.sh\''''
      }
    }

  }
  environment {
    CI = 'true'
  }
}