pipeline {
    agent any
   
    stages {
        stage('Build') {
            steps {
                echo "Initiation of the Building Process utilizing Maven."
                echo "The Building Stage has been successfully completed"
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "Initiation of the Unit Testing Process utilizing NUnit."
                echo "The Unit Testing Process has been successfully completed"
                echo "Initiation of the Integration Testing Process utilizing Selenium"
                echo "The Integration Testing Process has been successfully completed"
            }
            
       post {
        success {
            echo "The Unit and Integration Testing Phases have been successfully completed"
            emailext(
                to: 'viranthamudalige@gmail.com',
                subject:"The status of the Unit and Integration Tests:  ${currentBuild.result}",
                body:"Kindly refer to the log files to obtain additional details",
                attachLog: true
            )
        }
        failure {
            echo "The Unit and Integration Testing Phases have been failed"
            emailext(
                to: 'viranthamudalige@gmail.com',
                subject:"The status of the Unit and Integration Tests:  ${currentBuild.result}",
                body:"Kindly refer to the log files to obtain additional details.",
                attachLog: true
            )
        }
    }
        }

        stage('Code Analysis') {
            steps {
                echo "Code analysis started with Veracode"
                echo "Code analysis successfully completed"
            }
        }

        stage('Security Scan') {
            steps {
                echo "Security scans started with 42Crunch"
                echo "Security scans successfully completed"
            }
            
                   post {
        success {
            echo "Unit and Integration Tests stage SUCCEDED"  // Add this line for debugging
            emailext(
                to: 'viranthamudalige@gmail.com',
                subject:"Security Scan:  ${currentBuild.result}",
                body:"Please check the logs for details.",
                attachLog: true
            )
        }

        failure {
            echo "Security Scan Tests stage FAILED"  // Add this line for debugging
            emailext(
                to: 'viranthamudalige@gmail.com',
                subject:"Security Scan:  ${currentBuild.result}",
                body:"Please check the logs for details.",
                attachLog: true
            )
        }
    }
    }

        stage('Deploy to Staging') {
            steps {
                echo "Staging deployment started"
                echo "Deployed to AWS EC2 instance-id: i-4214535890abcdef0 staging server"
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Integration tests started with Selenium"
                echo "Integration tests completed successfully."
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Production deployment started"
                echo "Deployed to AWS EC2 instance-i-4214535890abcdef0 production server"
            }
}
}
}
