pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/tekin-worldpay/hello-world.git']]])
            }
        }
        stage('Build') {
            steps {
                sh "./gradlew build"
            }
        }
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('sonarqube') {
                  sh "./gradlew sonar"
                }
            }
        }
    }
}