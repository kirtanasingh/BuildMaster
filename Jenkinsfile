pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/kirtanasingh/BuildMaster.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Result') {
            steps {
                echo 'Build and Test completed successfully'
            }
        }
    }
}
