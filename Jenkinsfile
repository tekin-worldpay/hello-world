pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('SonarQube Analysis') {
            withSonarQubeEnv() {
              sh "./gradlew sonar"
            }
        }
    }
}