pipeline{
    agent any
    stages{
        stage('checkout'){
            steps{
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Ranashekar9666/taxi-booking-234.git']])
            }
        }
        stage('Build'){
            steps{
                sh "mvn package"
            }
        }
        stage('Deploy to tomcat'){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://13.53.212.204:8081/')], contextPath: 'dev', war: '**/*.war'
            }
        }
    }
}
