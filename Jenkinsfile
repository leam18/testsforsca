pipeline {
    agent any
    stages {
        stage('SCM') {
            steps {
                  git 'https://github.com/leam18/testsforsca.git'
                }
            }
        stage('SonarQube analysis') {
            def scannerhome = tool 'sonar-scanner';
            steps{
                withSonarQubeEnv ('SCA'){
                sh  "${scannerhome}bin/sonar-scanner javascript/"
                }
            }
        }
    }
}