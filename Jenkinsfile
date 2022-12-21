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
                  ansible-playbook /ansible/test.yml
                """
            }
        }
    }
}