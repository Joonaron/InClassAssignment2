pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', URL: 'https://github.com/Joonaron/InClassAssignment2.git'
            }
        }
        stage('Build') {
            steps {
                sh 'clean install'
            }
        }
        stage('Test') {
            steps {
                sh 'test'
            }
        }
        stage('Code Coverage') {
            steps {
                sh ' jacoco:report'
            }
        }
        stage('Publish Test Results') {
            steps {
                junit '**/target/surefire-reports/*.xml'
            }
        }
        stage('Publish Coverage Report') {
            steps {
                jacoco()
            }
        }
    }
}
