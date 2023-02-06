pipeline {
    agent any
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
            steps {
                bat 'echo Running unit tests'
            }
        }
        stage('Regression tests') {
            steps {
                bat 'echo Deploying build'
            }
        }
        stage('Release to pre-prod') {
            steps {
                bat 'echo Running E2E tests'
            }
        }
        stage('Release to prod') {
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
