pipeline {
  agent any
  stages {
    stage('Setup Local Environment') {
      steps {
        echo '--RUNNING LOCAL ENVIORNMENT --'
        sh ''' #!/bin/bash 
        sudo apt-get update
        sudo apt-get install \ 
        python3-dev libffi-dev gcc libssl-dev docker.io -y
        sudo apt install python3-pip -y
        sudo apt install python3.10-venv -y
        sudo python3 -m venv local
        source local/bin/activate
        ''' 
      }
    }
    stage('Deploy Infrastructure') {
      steps {
        echo '--Running Ansible Kolla Prechecks Script --'
        sh '''#!/bin/bash 
        kolla-ansible -i /etc/kolla/all-in-one deploy
        ''' 
      }
    }
  }
}
