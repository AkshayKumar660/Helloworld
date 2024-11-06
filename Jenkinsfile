pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                // Replace the URL with the SSH format and specify the credentials ID
                git url: 'git@github.com:BasavarajSamrat/my-maven-webap.git', credentialsId: 'your-ssh-key-id'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                sh 'npm start &'
            }
        }
    }
    post {
        success {
            echo 'Application deployed successfully!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
