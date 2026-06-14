pipeline {
    agent any

    stages {
        stage('Clonar código') {
            steps {
                git 'https://github.com/davidelezg-lab/demo-ci-devops.git'
            }
        }

        stage('Instalar dependencias') {
            steps {
                sh 'npm install'
            }
        }

        stage('Ejecutar app (test simple)') {
            steps {
                sh 'node app.js & sleep 5'
            }
        }
    }
}
