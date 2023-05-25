pipeline {
    agent any
    environment {
        PATH = "/opt/maven/bin:$PATH"
    }
    stages{
        stage("build code"){
            steps{
                sh 'mvn clean install'
            }
            
        }
        stage('SonarQube analysis') {
            steps{
                withSonarQubeEnv('sonarqube-lts-community'){
                    sh "mvn sonar:sonar"
                }
            }
        }
    }
}
