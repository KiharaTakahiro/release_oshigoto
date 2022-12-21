pipeline {
    agent any
    options {
        ansiColor('xterm')
    }
    stages {
        stage('test') {
            environment { 
                ANSIBLE_FORCE_COLOR=true 
            }
            steps {
                sh """
                  cd ansible
                  ansible-playbook test.yml
                """
            }
        }
    }
}