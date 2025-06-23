pipeline {
    agent { label 'AGENT-1' }
    environment { 
        PROJECT = 'EXPENSE'
        COMPONENT = 'BACKEND'
    }
    options {
        disableConcurrentBuilds()
        timeout(time: 5, unit: 'SECONDS')
    }
    stages {
        stage('Build') {
            steps {
                script {
                    sh """
                        echo "Hello this is Build"
                        echo "Project: $PROJECT"
                        sleep 15
                    """
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh """
                        echo "Hello this is Test"
                    """
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    sh """
                        echo "Hello this is Deploy"
                    """
                }
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'I will run when pipeline is failure'
        }
        success { 
            echo 'I will run when pipeline is success'
        }
    }
}