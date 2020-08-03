pipeline {
  agent any
  stages {
    stage('Pull code') {
      steps {
        git 'https://github.com/leam18/testsforsca.git'
      }
    }

    stage('SCA Scanning') {
      steps {
        withSonarQubeEnv('Sonarqube') {
          waitForQualityGate true
        }

      }
    }

  }
}