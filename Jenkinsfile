pipeline {
    agent any

    parameters {
        string(name: 'FILENAME', defaultValue: 'learn.txt', description: 'Enter file name')
        choice(name: 'ENV', choices: ['dev','qa','prod'], description: 'Select environment')
    }

    stages {
        stage('Read File') {
            steps {
                bat "type %FILENAME%"
            }
        }

        stage('Environment Logic') {
            steps {
                script {
                    if (params.ENV == 'dev') {
                        echo "Deploying to DEV environment"
                    }
                    else if (params.ENV == 'qa') {
                        echo "Deploying to QA environment"
                    }
                    else {
                        echo "Deploying to PROD environment"
                    }
                }
            }
        }

    }
}