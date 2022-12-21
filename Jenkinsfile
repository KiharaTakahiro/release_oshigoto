pipeline {
    agent any
    options {
        ansiColor('xterm')
    }
    parameters {
        choice(name: 'CHECK_MODE', choices: ['--check --diff', '--diff'], description: '')
    }
    stages {
        stage('test') {
            environment { 
                ANSIBLE_FORCE_COLOR=true
            }
            steps {
                sh """
                  rm -rf ansible/release_dir/
                  rm -rf event/
                  mkdir ansible/release_dir
                  git clone https://github.com/KiharaTakahiro/event.git
                  rm -rf event/.git
                  mv event/ ansible/release_dir/
                  ls -l ansible/release_dir/
                  pwd
                  cd ansible
                  ansible-playbook ${params.CHECK_MODE} test.yml
                """
            }
        }
    }
}