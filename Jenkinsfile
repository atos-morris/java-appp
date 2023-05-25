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
            def scannerHome = tool 'SonarScanner 4.0';
            steps{
                withSonarQubeEnv('eno-sonar'){
                    sh "mvn sonar:sonar"
                }
            }
        }
    }
}
