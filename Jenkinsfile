pipeline {
    agent any
    parameters {
        choice(name: 'NEW_VERSION' , choices: ['1.0', '2.0', '3.0'], description: 'Please chose between different version')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }

    stages {
        stage('Test') { 
            steps {
                script {
                    gv.testApp()
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    gv.buildApp()
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    gv.deployApp()
                }
            }
        }

        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
