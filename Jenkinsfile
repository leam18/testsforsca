def scannerhome = tool 'sonar-scanner'
pipeline {
    agent any
    stages {
        stage('SCM') {
            steps {
                  git 'https://github.com/leam18/testsforsca.git'
                }
            }
        stage('SonarQube analysis') {
            steps{
                withSonarQubeEnv ('SCA'){
                sh  "${scannerhome}bin/sonar-scanner javascript/"
                }
            }
        }
    }
}