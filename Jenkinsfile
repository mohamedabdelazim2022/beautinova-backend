pipeline {
    agent any
    environment {
        SERVER_CREDENTIALS = credentials('nova-credentials')
    } 
    stages {
        stage ("deploying"){
            steps{                
                sh 'cd /home/nova/beautinova-backend'
                sh 'sudo pkill node'
                sh 'sudo supervisorctl restart beautinova-api'
                sh 'sudo pkill node'
                echo "deploying with ${SERVER_CREDENTIALS}"
                sh "${SERVER_CREDENTIALS}"
            }
        }
    }
}