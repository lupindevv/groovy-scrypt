pipeline {
    agent any

    environment {
        NEW_VERSION = '1.1.0'
    }

    tools {
        maven "maven-build"
    }

    stages {
        stage('Test') {
            when {
                expression {
                    env.BRANCH_NAME == 'main'
                }
            }
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
                withCredentials([
                    usernamePassword(credentialsId: 'server-credentials', usernameVariable: 'USER', passwordVariable: 'PWD')
                ]) {
                    echo "Deploying with username ${env.USER}"
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
