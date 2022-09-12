pipeline {
    agent any

    stages {
        stage("Build") {
            options {
                timeout(time: 10, unit: 'MINUTES')
            }
            steps {
                sh 'Echo "Test"'
            }
        }
        stage("Deploy") {
            options {
                timeout(time: 10, unit: 'MINUTES')
            }
            steps {
                {
                    ansiblePlaybook(
                        credentialsId: 'tokyoKey',
                        playbook: 'main.yml',
                        inventory: 'hosts',
                        become: 'yes',
                    )
                }
            }
        }
    }
} 


