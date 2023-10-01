pipeline {
    agent any
   
    stages {
        stage('Build') {
            steps {
                echo "Initiation of the Building Process utilizing Maven."
                echo "Executing"
                echo "The Building Stage has been successfully concluded."
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "Initiation of the Unit Testing Process utilizing TestNG."
                echo "Executing"
                echo "The Unit Testing Process has been successfully concluded."
                echo "Initiation of the Integration Testing Process utilizing Selenium."
                echo "Executing"
                echo "The Integration Testing Process has been successfully concluded."
            }
            
       post {
        success {
            echo "The Unit and Integration Testing Phase has been successfully completed without any issue."
            emailext(
                to: 'viranthamudalige@gmail.com',
                subject:"The status of the Unit and Integration Test:  ${currentBuild.result}",
                body:"Kindly refer to the log files to obtain additional information about the process.",
                attachLog: true
            )
        }
        failure {
            echo "The Unit and Integration Testing Phase has failed."
            emailext(
                to: 'viranthamudalige@gmail.com',
                subject:"The status of the Unit and Integration Test:  ${currentBuild.result}",
                body:"Kindly refer to the log files to obtain additional information about the process.",
                attachLog: true
            )
        }
    }
        }

        stage('Code Analysis') {
            steps {
                echo "Initiation of the Code Analysis Process utilizing Sonar-Scanner."
                echo "The Code Analysis Process has been successfully concluded."
            }
        }

        stage('Security Scan') {
            steps {
                echo "Initiation of the Security Scanning Process utilizing Checkmarx."
                echo "The Security Scanning Process has been successfully completed."
            }
            
                   post {
        success {
            echo "The Security Scanning Process has been successfully completed."
            emailext(            
                to: 'viranthamudalige@gmail.com',
                subject:"The status of the Security Scanning Process:  ${currentBuild.result}",
                body:"Kindly refer to the log files to obtain additional details.",
                attachLog: true
            )
        }

        failure {
            echo "The Security Scanning Process has failed." 
            emailext(
                to: 'viranthamudalige@gmail.com',
                subject:"The status of the Security Scanning Process:  ${currentBuild.result}",
                body:"Kindly refer to the log files to obtain additional details.",
                attachLog: true
            )
        }
    }
    }

        stage('Deploy to Staging') {
            steps {
                echo "Commence the deployment to the staging environment."
                
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Initiation of the Integration Tests On Staging Process"
                echo "The Integration Tests On Staging have been successfully completed."
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Initiation of the Deployment To Production Process"
                echo "Utilize the AWS Command Line Interface (CLI) or an alternative deployment tool to facilitate deployment to the production environment."
            }
}
}
}
