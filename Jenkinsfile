pipeline {
    agent any

    parameters {
        string(name: 'FILENAME', defaultValue: 'learn.txt', description: 'Enter file name to read')
        choice(name: 'ENV', choices: ['dev','qa','prod'], description: 'Select environment')
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
                echo %ENV%
            }
        }

    }
}