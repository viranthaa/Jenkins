pipeline {
    agent any
   
    stages {
        stage('Build') {
            steps {
                echo "Code fetched from https://github.com/manubalhara/Jenkins-Project.git"
                echo "Building Initiated using Maven"
                echo "Build successful"
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "Unit tests Initiated with NUint"
                echo "Unit tests completed."
                echo "Integration tests started with Selenium"
                echo "Integration tests completed."
            }
            
       post {
        success {
            echo "Unit and Integration Tests stage SUCCEDED"  // Add this line for debugging
            emailext(
                to: 'viranthamudalige@gmail.com',
                subject:"Unit and Integration Tests Stage Status:  ${currentBuild.result}",
                body:"Please check the logs for details.",
                attachLog: true
            )
        }
        failure {
            echo "Unit and Integration Tests stage FAILED"  // Add this line for debugging
            emailext(
                to: 'viranthamudalige@gmail.com',
                subject:'Build Status:  ${currentBuild.result}',
                body:"Please check the logs for details.",
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
