pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                echo "This is a test stage."
            }
            post {
                always {
                    emailext(
                        to: "ananthvandothra@gmail.com",
                        subject: "Test Email",
                        body: "This is a test email from Jenkins."
                    )
                }
            }
        }
    }
}
