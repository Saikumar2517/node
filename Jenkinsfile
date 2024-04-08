pipeline {
    agent any 

    tools:{
        nodejs:'node'

    }
    stages{
        stage('checkout') {
            /* groovylint-disable-next-line NglParseError */
            checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'git-pass', url: 'https://github.com/Saikumar2517/node.git']])
        }

        stage('build') {
            sh 'npm install'
            sh 'npm run build'
        }
    }
}