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
                  git clone https://github.com/KiharaTakahiro/event.git
                  mv event/ ansible/release_dir/
                  cd ansible
                  ansible-playbook test.yml
                """
            }
        }
    }
}