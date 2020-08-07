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
                sh  "/var/jenkins_home/sonar-scanner/bin/sonar-scanner"
                }
            }
        }
        stage("Quality Gate") {
            steps {
              timeout(time: 5, unit: 'MINUTES') {
                waitForQualityGate abortPipeline: true
                }
            }   
        }
    }
}