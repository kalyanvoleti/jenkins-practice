pipeline {

    agent any
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
}