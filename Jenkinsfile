pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Check out the code from the Git repository
                git 'https://github.com/yourusername/your-repo.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    // Use the Maven tool configured in Jenkins
                    def mvnHome = tool 'Maven'
                    // Run Maven build
                    sh "${mvnHome}/bin/mvn clean install"
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Use the Maven tool configured in Jenkins
                    def mvnHome = tool 'Maven'
                    // Run Maven tests
                    sh "${mvnHome}/bin/mvn test"
                }
            }
        }

        stage('Deploy') {
            steps {
                docker pull python:latest
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded! Deploying to production...'
            // Additional deployment steps for production
        }
        failure {
            echo 'Pipeline failed!...'
            // Additional notification or rollback steps
        }
    }
}

