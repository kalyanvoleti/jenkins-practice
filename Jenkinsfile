pipeline {

    agent { label 'AGENT-1'}
    stages {
        stage('Build') {
                steps {
                    script {
                        sh """
                            echo "Hello Build"
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