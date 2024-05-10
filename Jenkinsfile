pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Stage 1: Build - Use tool like Maven to compile and package the code.'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Stage 2: Unit and Integration Tests - Using TestNG for unit tests and Selenium for integration tests.'
            }
            post {
                success {
                  
                        to: 'nairsuraj117@gmail.com',
                        subject: "Success - Unit and Integration Tests: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
                        body: "Unit and Integration Tests stage completed successfully.",
                        attachLog: true
                    
                }
                failure {
                  
                        to: 'nairsuraj117@gmail.com',
                        subject: "Failure - Unit and Integration Tests: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
                        body: "Unit and Integration Tests stage failed. Please check the attached logs.",
                        attachLog: true
                    
                }
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Code Analysis - Using Checkstyle to analyze code quality.'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Stage 4: Security Scan - Using tools like OWASP Dependency-Check to identify vulnerabilities.'
            }
            post {
                success {
                
                        to: 'nairsuraj117@gmail.com',
                        subject: "Success - Security Scan: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
                        body: "Security Scan stage completed successfully.",
                        attachmentsPattern: '**/*.log'
                    
                }
                failure {
                    
                        to: 'nairsuraj117@gmail.com',
                        subject: "Failure - Security Scan: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
                        body: "Security Scan stage failed. Please check the attached logs.",
                        attachmentsPattern: '**/*.log'
                    
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Stage 5: Deploy to Staging - Deploy to a staging server using Jenkins Deploy Plugin.'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Stage 6: Integration Tests on Staging - Run tests on the staging environment using Selenium.'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Stage 7: Deploy to Production - Deploy to a production server using Ansible or Jenkins Deploy Plugin.'
            }
        }
    }

    post {
        success {
            
                to: 'nairsuraj117@gmail.com',
                subject: "Pipeline Overall Success: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
                body: "The pipeline has completed successfully across all stages.",
                attachmentsPattern: '**/*.log'
            
        }
        failure {
            
                to: 'nairsuraj117@gmail.com',
                subject: "Pipeline Overall Failure: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
                body: "The pipeline has failed. Please review the attached logs.",
                attachmentsPattern: '**/*.log'
            
        }
    }
}
