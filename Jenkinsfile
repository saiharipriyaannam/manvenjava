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

    post {
        success {
            emailext(
                to: 'saiharipriyakrishna@gmail.com',
                subject: "Jenkins SUCCESS: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Build ${env.BUILD_NUMBER} completed successfully.\n\nJob: ${env.JOB_NAME}\nBuild URL: ${env.BUILD_URL}"
            )
        }

        failure {
            emailext(
                to: 'saiharipriyakrishna@gmail.com',
                subject: "Jenkins FAILURE: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Build ${env.BUILD_NUMBER} failed.\n\nJob: ${env.JOB_NAME}\nBuild URL: ${env.BUILD_URL}"
            )
        }
    }
}