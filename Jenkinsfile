pipeline {
    agent any
    stages {
        stage('Setup Local Environment') {
            steps {
                echo '--RUNNING LOCAL ENVIRONMENT --'
                sh '''
                sudo apt-get update
                sudo apt-get install -y python3-dev libffi-dev gcc libssl-dev docker.io
                sudo apt install -y python3-pip python3.10-venv
                
                python3 -m venv local
                . local/bin/activate
                '''
            }
        }
        stage('Deploy Infrastructure') {
            steps {
                echo '--Running Ansible Kolla Prechecks Script --'
                sh '''
                kolla-ansible -i /etc/kolla/all-in-one deploy
                '''
            }
        }
    }
}
