pipeline {
    agent {
        label 'AGENT-01'
    }

    options {
        timeout(time: 1, unit: 'SECONDS')
    }

    stages {
        stage('Build') {
            steps {
                sh 'echo This is build'
                sh 'sleep 10'
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