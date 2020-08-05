pipeline {
    agent any
    stages {
        stage('SCM') {
            steps {
                  git url 'https://github.com/leam18/testsforsca.git'
            }
        }
        stage('SonarQube analysis') {
            steps {
               def scannerHome = tool 'SonarQube Scanner 4.3.0.2102';
                withSonarQubeEnv() 
               }
            }
        }
        stage("Quality Gate") {
            steps {
                timeout(time: 1, unit: 'HOURS') {
                    // Parameter indicates whether to set pipeline to UNSTABLE if Quality Gate fails
                    // true = set pipeline to UNSTABLE, false = don't
                    waitForQualityGate abortPipeline: true
                }
            }
        }
    }