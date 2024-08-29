pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application with Maven'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis with SonarQube'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan with OWASP tool'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging server (AWS)'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production server (AWS)'
            }
        }
    }

    post {
        always {
            emailext (
                to: "ananthvandothra@gmail.com",
                subject: "Jenkins Build - ${currentBuild.fullDisplayName}",
                body: "Build ${currentBuild.currentResult}: Check console output at ${env.BUILD_URL} to view the results.",
                attachLog: true
            )
        }
    }
}

