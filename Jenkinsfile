pipeline {
    agent any

    tools {
        nodejs "Nodejs_Jenkins"
    }
    
    stages {
        stage('Install Dependencies') {
            steps {
                // Ejecuta el comando npm install para instalar las dependencias de npm
                script {
                    // Usa un shell compatible con versiones antiguas de Node.js
                    sh 'npm install'
                }
            }
        }
        
        stage('Test') {
            steps {
                // Ejecuta el comando npm test para ejecutar las pruebas
                script {
                    // Usa un shell compatible con versiones antiguas de Node.js
                    sh 'npm test --no-update-notifier'
                }
            }
        }
    }
    
    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
