pipeline {
    agent any

    parameters {
        string(name: 'FILENAME', defaultValue: 'learn.txt', description: 'Enter file name to read')
    }

    stages {


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