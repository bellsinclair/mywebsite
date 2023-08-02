pipeline {
    agent any

    environment {
        NODE_VERSION = 'NodeJS'
        PATH = "${tool name: NODE_VERSION}/bin:${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from your version control system
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install npm dependencies
                sh 'npm install'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                // Run SonarQube Scanner
                script {
                    def scannerHome = tool name: 'SonarQube', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
                    withSonarQubeEnv('SonarQube') {
                        sh "${scannerHome}/bin/sonar-scanner"
                    }
                }
            }
        }
    }
}
