pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    // Checkout the source code from the repository
                    checkout scm
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Example build steps for a Node.js project
                    sh 'npm install'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Example test execution for a Node.js project
                    sh 'npm test'
                }
            }
        }

        stage('Archive Artifacts') {
            steps {
                script {
                    // Archive deployable artifacts
                    archiveArtifacts 'path/to/artifacts/**/*'
                }
            }
        }
    }
}


