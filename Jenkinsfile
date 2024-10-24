pipeline {
    agent {
        docker {
          image 'openjdk:21'
          args '-v /home/jenkins/.m2:/root/.m2'
        }
    }

    stages {

        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/tekin-worldpay/hello-world.git']]])
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
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