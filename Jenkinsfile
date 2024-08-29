pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project using Maven...'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests using JUnit...'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Performing static code analysis using SonarQube...'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing security scan using OWASP Dependency-Check...'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying application to Staging (e.g., AWS EC2)...'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on the Staging environment...'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying application to Production (e.g., AWS EC2)...'
            }
        }
    }

    post {
        always {
            echo 'Pipeline Execution Completed!'
        }

        success {
            echo 'Sending success email...'
            emailext subject: "Jenkins Pipeline Success",
                      body: "The pipeline has completed successfully.",
                      to: 'auritro.sami@gmail.com'
        }

        failure {
            echo 'Sending failure email...'
            emailext subject: "Jenkins Pipeline Failed",
                      body: "The pipeline has failed. Please check the logs.",
                      to: 'auritro.sami@gmail.com',
                      attachLog: true
        }
    }
}
