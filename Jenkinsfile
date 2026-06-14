pipeline {
    agent any

    stages {

        stage('Instalar dependencias') {
            steps {
                bat 'npm install'
            }
        }

        stage('Test') {
            steps {
                bat 'npm test'
            }
        }

stage('SonarQube') {
    steps {
        withCredentials([string(credentialsId: 'sonar-token', variable: 'SONAR_TOKEN')]) {
            bat """
            sonar-scanner -Dsonar.login=%SONAR_TOKEN%
            """
        }
    }
}

    }
}