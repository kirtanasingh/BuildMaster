pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/kirtanasingh/BuildMaster.git'
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

        stage('Deploy to Tomcat') {
            steps {
                bat '''
                copy /Y target\\*.war C:\\tomcat\\webapps
                '''
            }
        }
    }

    post {
        success {
            echo 'Build, Test and Deployment Successful!'
        }
        failure {
            echo 'Pipeline Failed'
        }
    }
}
