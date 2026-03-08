pipeline {
    agent any

    parameters {
        string(name: 'IMAGE_NAME', 
               defaultValue: 'acidaes/businessnext-diagnostictools:1.0.2-cache',
               description: 'Enter full image name')
    }

    stages {

        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/gitshalabh/jenkins-demo.git'
            }
        }

        stage('Show YAML Before') {
            steps {
                bat 'type cache-diagnostic-job.yaml'
            }
        }

        stage('Update Image') {
            steps {
                bat '''
                powershell -Command "(Get-Content cache-diagnostic-job.yaml) -replace 'image: .*','image: %IMAGE_NAME%' | Set-Content cache-diagnostic-job.yaml"
                '''
            }
        }

        stage('Show YAML After') {
            steps {
                bat 'type cache-diagnostic-job.yaml'
            }
        }

        stage('Commit Changes') {
            steps {
                bat '''
                git config user.email "shalabhtyagi3@gmail.com"
                git config user.name "gitshalabh"
                git add cache-diagnostic-job.yaml
                git commit -m "Updated image via Jenkins pipeline"
                '''
            }
        }

        stage('Push Changes') {
            steps {
                bat 'git push origin main'
            }
        }

    }
}