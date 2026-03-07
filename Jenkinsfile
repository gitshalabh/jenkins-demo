pipeline {
    agent any

    parameters {
        string(name: 'FILENAME', defaultValue: 'learn.txt', description: 'Enter file name to read')
    }

    stages {

        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/gitshalabh/jenkins-demo.git'
            }
        }

        stage('List Files') {
            steps {
                bat 'dir'
            }
        }

        stage('Read File From Parameter') {
            steps {
                bat "type %FILENAME%"
            }
        }

    }
}