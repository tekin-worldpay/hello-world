pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv() {
                  sh "./gradlew sonar"
                }
            }
        }
    }
}