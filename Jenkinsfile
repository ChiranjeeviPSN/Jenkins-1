pipeline {
    agent {
        label 'AGENT-01'
    }

    options {
        timeout(time: 10, unit: 'MINUTES')
        disableConcurrentBuilds()
       // retry(2)
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['one', 'two', 'three'], description: 'pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'enter a password')
    }

    stages {
        stage('Build') {
            steps {
                sh 'echo This is build'
                //sh 'sleep 10'
            }
        }

        stage('Test') { 
            steps {
                sh 'echo This is test'
            }
        }

        stage('Deploy') {
            when {
                expression { env.GIT_BRANCH != "origin/main" }
            }
            steps {
                sh 'echo This is deploy'
                //error 'pipeline failed'
            }
        }

        stage('Print params') {
            steps {
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
            }
        }

        stage('Approval') {
            input {
                message "Should we continue ?"
                ok "Yes. we should"
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should i say hello to ?')
                }
            }
                steps {
                    echo "Hello, ${PERSON}, nice to meet you"
                }
            }
    }
}    