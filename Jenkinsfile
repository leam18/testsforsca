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
                sh  "/var/jenkins_home/sonar-scanner/sonar-scanner-4.4.0.2170/bin/sonar-scanner"
                }
            }
        }
    }
}