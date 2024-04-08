pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout your code from your version control system
                git 'https://github.com/Saikumar2517/node.git'
            }
        }
        stage('Install dependencies') {
            steps {
                // Use npm to install dependencies
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                // Build your Node.js application (if necessary)
                sh 'npm run build'
            }
        }
     
    }

   
}
