pipeline {
    agent any

    tools {
        maven 'maven latest' // Ensure this is configured in Jenkins > Global Tool Config
    }

    stages {
        stage('Source') {
            steps {
                echo 'Cloning source code...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                sh 'echo "Deployed successfully!"'
            }
        }
    }
}
