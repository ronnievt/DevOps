pipeline {
    agent any

    stages {
        stage('Подготовка окружения') {
            steps {
                ansiblePlaybook(
                    playbook: 'firstPlaybook.yml',
                    inventory: 'inventory/stend1/hosts',
                    credentialsId: 'ansible-ssh-keys',
                    tags: 'prepare'
                )
            }
        }

        stage('Запуск приложений') {
            steps {
                ansiblePlaybook(
                    playbook: 'firstPlaybook.yml',
                    inventory: 'inventory/stend1/hosts',
                    credentialsId: 'ansible-ssh-keys',
                    tags: 'deploy'
                )
            }
        }
    }
}
