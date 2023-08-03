pipeline {
  agent any

  stages {
    stage('SonarQube analysis') {
      steps {
        withSonarQubeEnv(credentialsId: 'sonarqube-token', installationName: 'sonarqube') {
          sh 'sonar-scanner'
        }
      }
    }
  }
}