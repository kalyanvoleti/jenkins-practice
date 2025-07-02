pipeline {

    agent { label 'AGENT-1'}
    environment {
        PROJECT = 'EXPENSE'
        COMPONENT = 'FRONTEND'
    }
    options {
         disableConcurrentBuilds()
         timeout(time: 30, unit: 'MINUTES')
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Build') {
                steps {
                    script {
                        sh """
                            echo "Hello Build"
                            echo "PROJECT: $PROJECT"
                            echo "Hello ${params.PERSON}"

                            echo "Biography: ${params.BIOGRAPHY}"

                            echo "Toggle: ${params.TOGGLE}"

                            echo "Choice: ${params.CHOICE}"

                            echo "Password: ${params.PASSWORD}"
                        """
                    }
                }
        }
        stage('Deploy') {
                input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
                }
                steps {
                    script {
                        sh """
                            echo "Hello Deploy"
                        """
                    }
                }
        }
        stage('Test') {
                steps {
                    script {
                        sh """
                            echo "Hello Test"
                        """
                    }
                }
        }
    }
    post {
        always {
            echo "i also say Hello"
        }
        success {
            echo "i will run when the pipeline is success"
        }
        failure {
            echo "i will run when the pipeline is failure"
        }
    }
}