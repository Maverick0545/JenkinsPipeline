pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building the code using Maven" // Example: Maven
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit tests and integration tests" // Example: JUnit for unit tests, Selenium for integration tests
            }
        }

        stage('Code Analysis') {
            steps {
                echo "Running code analysis using SonarQube" // Example: SonarQube
            }
        }

        stage('Security Scan') {
            steps {
                echo "Performing security scan using OWASP ZAP" // Example: OWASP ZAP
            }
            post {
                success {
                    mail to: "bhavesh53500@gmail.com",
                    subject: "Pipeline Success: ${currentBuild.fullDisplayName}",
                    body: "The pipeline executed successfully."
                
                }
                failure {
                    mail to: "bhavesh53500@gmail.com",
                    subject: "Pipeline Failure: ${currentBuild.fullDisplayName}",
                    body: "The pipeline failed. Please check the logs for details."
                    
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Deploying the application to staging server (e.g., AWS EC2)" // Example: AWS CodeDeploy
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on staging environment" // Example: Selenium
            }
           post {
                success {
                    mail to: "bhavesh53500@gmail.com",
                    subject: "Pipeline Success: ${currentBuild.fullDisplayName}",
                    body: "The pipeline executed successfully."
                
                }
                failure {
                    mail to: "bhavesh53500@gmail.com",
                    subject: "Pipeline Failure: ${currentBuild.fullDisplayName}",
                    body: "The pipeline failed. Please check the logs for details."
                    
                }
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to production server (e.g., AWS EC2)" // Example: AWS CodeDeploy
            }
        }
    }
}
