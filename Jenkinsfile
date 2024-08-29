pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building the code using Maven."
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit and integration tests."
            }
            post {
                success {
                    mail to: "ananthvandothra@gmail.com",
                    subject: "Successful Unit and Integration Tests Stage",
                    body: "The Unit and Integration Tests stage completed successfully!",
                    attachLog: true
                }
                failure {
                    mail to: "ananthvandothra@gmail.com",
                    subject: "Failed Unit and Integration Tests Stage",
                    body: "The Unit and Integration Tests stage failed.",
                    attachLog: true
            }
        }

        stage('Code Analysis') {
            steps {
                echo "Analyzing code quality with SonarQube."
            }
        }

        stage('Security Scan') {
            steps {
                echo "Performing a security scan with OWASP ZAP or Snyk."
            }
            post {
                success {
                    mail to: "ananthvandothra@gmail.com",
                    subject: "Successful Security Scan",
                    body: "The Security Scan stage completed successfully!",
                    attachLog: true
                }
                failure {
                    mail to: "ananthvandothra@gmail.com",
                    subject: "Failed Security Scan Stage",
                    body: "The Security Scan stage failed.",
                    attachLog: true
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Deploying the application to a staging server (e.g., AWS EC2)."
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on the staging environment."
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to a production server (e.g., AWS EC2)."
            }
        }
    }
}

