#pipeline {
#    agent any
#    stages {
#        stage('Setup Local Environment') {
#            steps {
#                echo '--RUNNING LOCAL ENVIRONMENT --'
#                sh '''#!/bin/bash
#		echo $USER
#                echo $PATH
#                sudo apt update
#                sudo /usr/bin/apt-get install python3-dev libffi-dev gcc libssl-dev -y
#                sudo apt-get install python3-pip -y
#                sudo apt-get install python3.10-venv -y
#                python3 -m venv local
#                source local/bin/activate
#                '''
#            }
#        }
#    }
#}



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

