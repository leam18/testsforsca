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
                def scannerhome = tool 'sonar-scanner'
                withSonarQubeEnv ('SCA'){
                sh  "${scannerhome}bin/sonar-scanner javascript/"
                }
            }
        }
    }
}