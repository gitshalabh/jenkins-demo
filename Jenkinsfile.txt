pipeline {
    agent any

    stages {

        stage('List Files') {
            steps {
                bat 'dir'
            }
        }

        stage('Read File') {
            steps {
                bat 'type learn.txt'
            }
        }

    }
}