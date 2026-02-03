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
                bat 'mvn clean compile'
            }
        }

        stage('Run') {
            steps {
                bat 'java -cp target/classes com.buildmaster.App'
            }
        }
    }
}
