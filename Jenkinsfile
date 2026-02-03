pipeline {
    agent any

    tools {
        jdk 'JDK'
        maven 'Maven'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
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
                echo Deploying BuildMaster.war to Tomcat...
                dir target
                copy /Y "target\\BuildMaster.war" "C:\\Program Files\\apache-tomcat-9.0.115\\webapps\"
                '''
            }
        }
    }

    post {
        failure {
            echo 'Pipeline Failed'
        }
        success {
            echo 'Pipeline Successful'
        }
    }
}
