pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'whoami'
                sh 'npm --version'
                sh 'npm install'
            }
        }
        stage('test') {
            steps {
                sh 'npm test'
            }
        }
        stage('deploy') {
            steps {
                input message: 'Deploy this build?', ok: 'Publish' 
                echo 'deployed'
            } 
        }
    }
}
