pipeline {
    agent any

    tools {
        nodejs 'node'
    }
    stages {
        stage('Checkout') {
            steps {
                // Checkout your code from your version control system
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'git-pass', url: 'https://github.com/Saikumar2517/node.git']])
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

            stage('test') {
                steps {
                    script {
                        def scannerHome = tool 'sonar'
                        withSonarQubeEnv(credentialsId: 'sonar-pass') {
                            sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=node"
                        }
                    }
                }
            }
        }
    }
}
