pipeline {

    agent { label 'AGENT-1'}
    environment {
        PROJECT = 'EXPENSE'
        COMPONENT = 'BACKEND'
    }
    stages {
        stage('Build') {
                steps {
                    script {
                        sh """
                            echo "Hello Build"
                            echo "PROJECT: $PROJECT"
                        """
                    }
                }
        }
        stage('Deploy') {
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