pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Check out your source code from version control
                git url: 'https://github.com/Prabakaran2596/CICD.git'
            }
        }

        stage('Build') {
            steps {
                // Build your code (e.g., compile, package)
                sh 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy your code (e.g., copy to server)
                sh 'scp target/yourapplication.war ubuntu@ec2-65-0-95-229.ap-south-1.compute.amazonaws.com:/home/ubuntu'
            }
        }

        stage('Run') {
            steps {
                // Start your application
                sh 'ssh ubuntu@ec2-65-0-95-229.ap-south-1.compute.amazonaws.com "/home/ubuntu/start-script.sh"'
            }
        }
    }
}
