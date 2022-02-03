pipeline {
  agent any
  stages {
    stage('Init') {
      agent {
        docker {
          image 'ppiper/cf-cli:v8'
        }

      }
      steps {
        sh 'cf login -a ${SCP_API_URL} -u ${SCP_USER} -p ${SCP_PASS} -o ${SCP_ORG} -s ${SCP_SPACE}'
        git(url: 'https://github.com/jiaroa/fiori.gwsample.git', branch: 'master', credentialsId: 'GitHubBasicAuthJiaroa', changelog: true)
      }
    }

    stage('Build') {
      steps {
        echo 'Vamos a hacer el build'
        mtaBuild(script: this, buildTarget: 'CF')
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