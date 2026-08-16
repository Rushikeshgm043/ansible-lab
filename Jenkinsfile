
pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/yourusername/ansible-lab.git'
            }
        }

        stage('Connectivity Test') {
            steps {
                sh 'ansible all -m ping'
            }
        }

        stage('Manage Postfix') {
            steps {
                sh 'ansible-playbook playbooks/postfix.yml'
            }
        }

        stage('Check Zimbra') {
            steps {
                sh 'ansible-playbook playbooks/zimbra.yml'
            }
        }
    }
}
