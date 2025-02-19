pipeline {
    agent any
    parameters {
        choice(name: 'NEW_VERSION' , choices: ['1.0', '2.0', '3.0'], description: 'Please chose between different version')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }

    stages {
        stage('Test') { 
            steps {
                echo 'Testing the application...'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                echo "Building the application with ${NEW_VERSION}"
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                echo "deploying version${params.NEW_VERSION}"
            }
        }

        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
