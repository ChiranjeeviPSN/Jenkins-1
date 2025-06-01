pipeline {
    agent {
        label 'AGENT-01'
    }

    stages {
        stage('Build'){
            sh 'echo This is build'
        }

        stage('Test'){
            sh 'echo This is test'
        }

        stage('Deploy') {
            sh 'echo This is deploy'
            error 'pipeline failed'
        }
    }
}