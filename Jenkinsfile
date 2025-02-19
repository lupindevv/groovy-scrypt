pipeline {
    agent any
    environment {
        NEW_VERSION = '1.1.0'
        tools {
            maven: "maven-build"
        }

    }

    stages {
        stage('test') {
            when {
                expression {
                    BRANCH_NAME == 'dev'
                }
            }
            steps {
                echo 'testing the application ..'
            }
        }
    }
    
        stage('build') {
            steps {
                echo 'building the application...'
                echo 'building the application with ${NEW_VERSION}'

            }
        }
    
    
        stage('deploy') {
            steps {
                echo 'deploying the application...'
                withCredentials([
                    usernamePassword(credentials: 'server-credentials' , usernameVariable: USER , passwordVarialbe: PWD)
                ])
            }
        }
    
    stage 
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    
}
