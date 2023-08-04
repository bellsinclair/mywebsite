pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building...'
      }
    }
    stage('Test') {
      steps {
        echo 'Testing Testing...'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying...'
      }
    }
    stage('Docker pull') {
      steps {
        sh 'docker pull jenkins/jenkins'
        sh 'docker images'
      }
    }
    stage('Docker run') {
      steps {
        sh 'sudo docker run jenkin -P jenkins/jenkins'
      }
    }
    
  }
}
