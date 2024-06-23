pipeline {
    agent any

    tools {
        nodejs "NodeJS 14"
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/felipe-murcia/jenkins-react.git'
            }
        }

        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                // Agrega tus pasos de despliegue aquí
                // Por ejemplo, copiar archivos al servidor de producción
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'build/**', allowEmptyArchive: true
            junit 'test-results.xml'
        }
    }
}
