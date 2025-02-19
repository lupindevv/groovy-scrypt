pipeline {
    agent any
    parameters {
        choice(name: 'NEW_VERSION' , choices: ['1.0', '2.0', '3.0'], description: 'Please chose between different version')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }

    stages {
        stage('init groovy script') {
            steps {
                script{
                    gv = load "script.groovy"
                }
            }
        }
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
            input {
                message "Select the environment to deploy"
                ok "Done"
                parameters{
                    choice(name: 'ENV', choices: ['DEV', 'QA', 'PROD'], description: 'Please select the environment')
                }
            }
            steps {
                script {
                    gv.deployApp()
                    echo "Deploying to ${params.ENV}"
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
