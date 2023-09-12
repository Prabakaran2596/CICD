pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Check out your source code from version control
                git url: 'https://github.com/yourusername/yourrepository.git'
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
                sh 'scp target/yourapplication.war user@yourserver:/path/to/deployment/directory'
            }
        }

        stage('Run') {
            steps {
                // Start your application
                sh 'ssh user@yourserver "/path/to/start-script.sh"'
            }
        }
    }
}
