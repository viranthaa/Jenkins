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
                
                echo "Initiation of the Integration Testing Process utilizing JMeter."
                echo "Executing"
                
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
                echo "Initiation of the Code Analysis Process utilizing Fortify."
                echo "Executing"
                echo "The Code Analysis Process has been successfully concluded."
            }
        }

        stage('Security Scan') {
            steps {
                echo "Initiation of the Security Scanning Process utilizing Checkmarx."
                echo "Executing"
                
            }
            
                   post {
        success {
            echo "The Security Scanning Process has been successfully completed without any issue."
            emailext(            
                to: 'viranthamudalige@gmail.com',
                subject:"The status of the Security Scanning Process:  ${currentBuild.result}",
                body:"Kindly refer to the log files to obtain additional information about the process.",
                attachLog: true
            )
        }

        failure {
            echo "The Security Scanning Process has failed." 
            emailext(
                to: 'viranthamudalige@gmail.com',
                subject:"The status of the Security Scanning Process:  ${currentBuild.result}",
                body:"Kindly refer to the log files to obtain additional information about the process.",
                attachLog: true
            )
        }
    }
    }

        stage('Deploy to Staging') {
            steps {
                echo "Commence the Deployment To The Staging Environment."
                echo "Executing"
                echo "The Deployment To The Staging Environment has been successfully concluded."
                
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Initiation of the Integration Tests On Staging Process."
                echo "Executing"
                echo "The Integration Tests On Staging has been successfully concluded."
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Initiation of the Deployment To Production Process."
                echo "Executing"
                echo "Utilize the AWS Command Line Interface (CLI) or an alternative deployment tool to facilitate deployment to the production environment."
            }
}
}
}
