pipeline {
    agent any

    tools {
    maven 'maven latest' // name must match Jenkins config
}

    environment {
        main = "${env.GIT_BRANCH}".replaceAll('origin/', '')
    }

    stages {
        stage('Source') {
            steps {
                echo "Branch detected: ${main}"
                echo 'Cloning source code...'
                git branch: "${main}", url: 'https://github.com/onkar12002/java-cicd-demo.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building branch: ${main}"
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests for: ${main}"
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying branch: ${main}"
                // Replace with real deploy commands
                sh 'echo Deploying...'
            }
        }
    }
}
