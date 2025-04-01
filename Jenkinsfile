pipeline {
    agent any
    stages {
        stage('Setup Local Environment') {
            steps {
                echo '--RUNNING LOCAL ENVIRONMENT --'
                sh'''#!/bin/bash
                pwd
                sudo apt install git python3-dev libffi-dev gcc libssl-dev -y
                sudo apt install python3-virtualenv -y
                virtualenv kolla-env
                source kolla-env/bin/activate
                pip install -U pip
                pip install 'ansible-core>=2.16,<2.17.99'
                git clone --branch main https://github.com/yashar-ansary/openstack-devops.git
                pip install ./openstack-devops
                sudo mkdir -p /etc/kolla
                sudo chown $USER:$USER /etc/kolla
                cp -r etc/kolla/* /etc/kolla
                cp openstack-devops/ansible/inventory/* /etc/kolla
                kolla-ansible install-deps
                cd openstack-devops/tools
                ./generate_passwords.py
                cd
                kolla-ansible bootstrap-servers -i /etc/kolla/all-in-one
                kolla-ansible prechecks -i /etc/kolla/all-in-one
                kolla-ansible deploy -i /etc/kolla/all-in-one
                pip install python-openstackclient -c https://releases.openstack.org/constraints/upper/2024.2
                kolla-ansible post-deploy

                '''
            }
        }

    }
}
