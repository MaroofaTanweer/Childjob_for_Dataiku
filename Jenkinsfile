pipeline {
    agent {
        docker { image 'python:3.9.16-slim' }
    }
    stages {
        stage('pre -build') {
            steps {
                bat 'echo Pre-build'
            }
        }
        stage('Unit tests') {
            steps {
                bat 'echo Build in progress.'
            }
        }
        stage('Package and Publish') {
            when {
                expression { 
                   return params.ENV_NAME == 'SIT'
                }

            }
            steps {
                bat 'echo Running unit tests'
            }
        }
        stage('Regression tests') {
            when {
                expression { 
                   return params.ENV_NAME == 'SIT'
                }
            }
            steps {
                bat 'echo Deploying build'
            }
        }
        stage('Release to pre-prod') {
            when {
                expression { 
                   return params.ENV_NAME == 'SIT'
                }
            }
            steps {
                bat 'echo Running E2E tests'
            }
        }
        stage('Release to prod') {
            when {
                 expression { 
                   return params.ENV_NAME == 'PROD'
                }
            }
            steps {
                bat 'echo Releasing to prod'
            }
        }
    }
 post {
        always {
            echo 'Cleanup after everything!'
        }
    }
}
