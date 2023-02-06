pipeline {
    agent {
        docker { image 'python:3.9.16-slim' }
    }
    stages {
        stage('pre -build') {
            steps {
                sh """
                echo 'Pre-build'
                """
            }
        }
        stage('Unit tests') {
            steps {
                sh """
                echo 'Build in progress.'
                """
            }
        }
        stage('Package and Publish') {
            when {
                expression { 
                   return params.ENV_NAME == 'SIT'
                }

            }
            steps {
                sh """
                echo 'Running unit tests'
                """
            }
        }
        stage('Regression tests') {
            when {
                expression { 
                   return params.ENV_NAME == 'SIT'
                }
            }
            steps {
                sh """
                echo 'Deploying build'
                """
            }
        }
        stage('Release to pre-prod') {
            when {
                expression { 
                   return params.ENV_NAME == 'SIT'
                }
            }
            steps {
                sh """
                echo 'Running E2E tests'
                """
            }
        }
        stage('Release to prod') {
            when {
                 expression { 
                   return params.ENV_NAME == 'PROD'
                }
            }
            steps {
                sh """
                echo 'Releasing to prod'
                """
            }
        }
    }
 post {
        always {
            echo 'Cleanup after everything!'
        }
    }
}
