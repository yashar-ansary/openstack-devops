pipeline {
    agent any
    stages {
        stage('Debug') {
            steps {
                sh'''
                apt update
                apt install python3-pip
                '''
            }
        }
    }
}

