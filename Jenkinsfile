pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Stage: Build'
                echo 'Task: Compiling and packaging the source code into a deployable artifact.'
                echo 'Tool: Maven'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Stage: Unit and Integration Tests'
                echo 'Task: Running unit tests on individual components and integration tests across components.'
                echo 'Tools: JUnit (unit tests), Postman/Newman (integration tests)'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Stage: Code Analysis'
                echo 'Task: Analysing code for smells, complexity, duplication and standards compliance.'
                echo 'Tool: SonarQube'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Stage: Security Scan'
                echo 'Task: Scanning code and dependencies for known vulnerabilities.'
                echo 'Tool: OWASP Dependency-Check'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Stage: Deploy to Staging'
                echo 'Task: Deploying the build to a staging server that mirrors production.'
                echo 'Tool: AWS EC2 (via Ansible)'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Stage: Integration Tests on Staging'
                echo 'Task: Running integration tests against the staging environment.'
                echo 'Tool: Selenium'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Stage: Deploy to Production'
                echo 'Task: Deploying the verified build to the live production server.'
                echo 'Tool: AWS EC2 (via Ansible)'
            }
        }
    }

    post {
        success { echo 'Pipeline completed successfully.' }
        failure { echo 'Pipeline failed.' }
    }
}