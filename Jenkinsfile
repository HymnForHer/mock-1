pipeline {
    agent any

    stages {
        stage("Build") {
            options {
                timeout(time: 10, unit: 'MINUTES')
            }
            steps {
                sh 'echo "Test"'
            }
        }
        stage("Deploy") {
            options {
                timeout(time: 10, unit: 'MINUTES')
            }
            steps {
                ansiblePlaybook(
                    credentialsId: 'TokyoKey',
                    disableHostKeyChecking: true,
                    installation : "Ansible",
                    playbook: 'main.yml',
                    inventory: 'hosts',
                    become: 'yes',
                )
            }
        }
    }
} 


