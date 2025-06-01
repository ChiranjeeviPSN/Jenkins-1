pipeline {
    agent {
        label 'AGENT-01'
    }

    options {
        timeout(time: 10, unit: 'SECONDS')
    }
    
    stages {
        stage('Build') {
            steps {
                sh 'echo This is build'
            }
        }

        stage('Test') { 
            steps {
                sh 'echo This is build'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo This is build'
                //error 'pipeline failed'
            }
        }
    }
}