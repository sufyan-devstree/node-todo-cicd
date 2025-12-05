pipeline {
    agent any

    stages {
        stage('Deploy to Dev Server') {
            steps {
                // Use the Jenkins SSH credentials
                sshagent(['dev-server-credentials']) {
                    sh '''
                        ssh -o StrictHostKeyChecking=no ubuntu@13.126.139.109 "
                            cd /home/node/node-todo-cicd &&
                            sudo git pull origin master &&
                            pm2 restart 1
                        "
                    '''
                }
            }
        }
    }
}
