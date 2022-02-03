pipeline {
  agent any
  stages {
    stage('Init') {
      agent {
        docker {
          image 'node:16.13.1-alpine'
        }

      }
      steps {
        sh 'node --version'
      }
    }

  }
  environment {
    bluild_tool = 'npm'
    gitFolder = ''
    gitCredential = ''
    SCP_API_URL = 'https://api.cf.us10.hana.ondemand.com'
    SCP_USER = '1joandre@gmail.com'
    SCP_PASS = '98Jfgn78r9$'
    SCP_ORG = '66de7174trial'
    SCP_SPACE = 'dev'
  }
}