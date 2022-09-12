pipeline{
    agent any  
    stages{
        stage("Build"){
            steps{
                echo "========Building Images......========"
            }
        }

        // stage("Test"){
        //     steps{
        //         echo "====++++executing A++++===="
        //     }
        // }

        stage("Deploy"){ 
            steps{
                ansiblePlaybook(
                    credentialsId: 'tokyo-key',
                    playbook: 'main.yml',
                    inventory: 'hosts',
                    become: yes
                )
                echo "========Building Images......========"
                sh "ansible-playbook test -i hosts"
            }
        }
    }
}
