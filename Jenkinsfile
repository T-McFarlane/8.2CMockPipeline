/*
 * SIT223 - 8.2C
 * Part 1, Task 1: GitHub Integration - Mock 7-Stage Pipeline
 *
 * Author: Tom McFarlane
 *
 * This is a MOCK pipeline: per the task instructions, each stage only
 * prints (a) the task it represents and (b) the tool that would be used
 * to perform that task in a real pipeline. No tools are actually invoked.
 *
 * Trigger: the task explicitly says a webhook is NOT required - polling
 * the GitHub repo on a schedule is sufficient, so this uses pollSCM().
 */
 
pipeline {
    agent any
 
    triggers {
        // Poll the GitHub repository for new commits every 5 minutes.
        // (Webhook integration is not required for this task.)
        pollSCM('H/5 * * * *')
    }
 
    stages {
 
        stage('Build') {
            steps {
                echo 'Task: Build the code using a build automation tool to compile and package the application.'
                echo 'Tool: Maven'
            }
        }
 
        stage('Unit and Integration Tests') {
            steps {
                echo 'Task: Run unit tests to ensure the code functions as expected.'
                echo 'Tool: JUnit'
                echo 'Task: Run integration tests to ensure the different components of the application work together as expected.'
                echo 'Tool: Postman/Newman'
            }
        }
 
        stage('Code Analysis') {
            steps {
                echo 'Task: Analyse the code to ensure it meets industry coding standards.'
                echo 'Tool: SonarQube'
            }
        }
 
        stage('Security Scan') {
            steps {
                echo 'Task: Perform a security scan on the code to identify known vulnerabilities.'
                echo 'Tool: OWASP Dependency-Check'
            }
        }
 
        stage('Deploy to Staging') {
            steps {
                echo 'Task: Deploy the application to a staging server.'
                echo 'Tool: Ansible (targeting an AWS EC2 staging instance)'
            }
        }
 
        stage('Integration Tests on Staging') {
            steps {
                echo 'Task: Run integration tests on the staging environment to confirm the application behaves as expected in a production-like environment.'
                echo 'Tool: Selenium'
            }
        }
 
        stage('Deploy to Production') {
            steps {
                echo 'Task: Deploy the application to the production server.'
                echo 'Tool: Ansible (targeting an AWS EC2 production instance)'
            }
        }
    }
 
    post {
        success {
            echo 'Mock pipeline completed successfully.'
        }
        failure {
            echo 'Mock pipeline failed. Please check the logs above for details.'
        }
    }
}
