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
                script {
                    def scannerHome = tool name: 'SonarScanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
                    withSonarQubeEnv('SonarCloud') {
                        bat "\"${scannerHome}\\bin\\sonar-scanner.bat\" -Dsonar.login=%SONAR_AUTH_TOKEN%"
                    }
                }
            }
        }
    }
}