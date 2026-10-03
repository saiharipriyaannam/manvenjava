pipeline {
    agent any

    tools {
        maven 'Maven3.9.11'
    }

    stages {

        stage('Clean') {
            steps {
                bat "mvn clean"
            }
        }

        stage('Install') {
            steps {
                bat "mvn install"
            }
        }

        stage('Test') {
            steps {
                bat "mvn test"
            }
        }

        stage('Package') {
            steps {
                bat "mvn package"
            }
        }
    }
}