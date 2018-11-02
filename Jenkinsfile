pipeline {
  agent {
    node {
      label 'ecs-cluster'
    }

  }
  stages {
    stage('Prepare Production') {
      parallel {
        stage('Prepare Repo') {
          steps {
            git(credentialsId: '40094f04-235d-4342-8fa9-6bc6a368b8d9', url: 'git@github.com:mulesoft-consulting/1platform-sys-notification-api-for-twilio.git')
          }
        }
        stage('Prepare Development') {
          steps {
            git(url: 'git@github.com:mulesoft-consulting/1platform-sys-notification-api-for-twilio.git', branch: 'develop', credentialsId: '40094f04-235d-4342-8fa9-6bc6a368b8d9')
          }
        }
      }
    }
  }
}