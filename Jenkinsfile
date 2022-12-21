pipeline {
    agent any
    options {
        ansiColor('xterm')
    }
    parameters {
        choice(name: 'CHECK_MODE', choices: ['--check --diff', ''], description: '')
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
                  ansible-playbook ${params.CHECK_MODE} test.yml
                """
            }
        }
    }
}