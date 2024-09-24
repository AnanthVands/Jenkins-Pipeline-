pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *')
    }

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
                    emailext attachLog: true, 
                    body: 'The Unit and Integration Tests stage completed successfully!',  
                    subject: 'Successful Unit and Integration Tests Stage', 
                    to: 'ananthvandothra@gmail.com'
                }
                failure {
                    emailext attachLog: true, 
                    body: 'The Unit and Integration Tests stage failed.', 
                    subject: 'Failed Unit and Integration Tests Stage', 
                    to: 'ananthvandothra@gmail.com'
                }
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
                    emailext attachLog: true, 
                    body: 'The Security Scan stage completed successfully!', 
                    subject: 'Successful Security Scan', 
                    to: 'ananthvandothra@gmail.com'
                }
                failure {
                    emailext attachLog: true, 
                    body: 'The Security Scan stage failed.', 
                    subject: 'Failed Security Scan Stage', 
                    to: 'ananthvandothra@gmail.com'
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
