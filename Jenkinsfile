pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Utilize Maven as a build automation and project management tool."
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Utilize the NPM Test command."
            }
            
        }
        stage('Code Analysis') {
            steps {
                echo "Please consider giving Sonar-Scanner a try."
            }
        }
        stage('Security Scan') {
            steps {
                echo "Utilize a security scanning tool to detect potential security weaknesses."
                echo "Performing a test with the npm audit command."
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Utilize the AWS CLI or an alternative deployment tool for staging deployment."
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Executing"
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Utilize the AWS CLI or an alternative deployment tool for deploying to the production environment."
            }
        }
    }
    post {
        success {
                mail to:"viranthamudalige@gmail.com",
                subject: "Build Completed Successfully: ${currentBuild.fullDisplayName}",
                body: "The build has been completed without any issues."
                }
        }
}
