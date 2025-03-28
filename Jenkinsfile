pipeline {
    agent any
    stages {
        stage('Debug') {
            steps {
                sh 'echo $PATH'
                sh 'ls -l /usr/bin/apt-get'
                sh 'which apt-get || echo "apt-get not found"'
                sh 'sudo apt-get --version || echo "sudo apt-get not working"'
            }
        }
    }
}

