pipeline {
    agent any
     environment {
        // Define environment variables if needed
        SERVER_IP = 'ec2-3-109-143-60.ap-south-1.compute.amazonaws.com'
        SERVER_PORT = '22'
        USERNAME = 'ubuntu'
        PRIVATE_KEY = credentials('0d955b09-6689-4fb8-9999-0b3fd8fe2b51') // Use Jenkins credentials to securely store the private key
     }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy to server') {
            steps {
                 script {
                    // Start an SSH agent using the private key
                    sshagent(['0d955b09-6689-4fb8-9999-0b3fd8fe2b51']) {
                        // Define the SSH command to execute on the server
                        sh "ssh -o StrictHostKeyChecking=no -l $USERNAME -p $SERVER_PORT $SERVER_IP 'cd /home/test && git pull origin main && ./deploy_script.sh'"
                    }
                 }
            }
        }
    }
}
