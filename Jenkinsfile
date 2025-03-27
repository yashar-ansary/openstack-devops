pipeline {
    agent any
    stages {
        stage('Setup Local Environment') {
            steps {
                echo '--RUNNING LOCAL ENVIRONMENT --'
                sh '''
		echo $USER
                sudo apt update
                sudo apt-get install python3-dev libffi-dev gcc libssl-dev -y
                sudo apt-get install python3-pip -y
                sudo apt install python3.10-venv -y
                python3 -m venv local
                source local/bin/activate
                '''
            }
        }
    }
}
