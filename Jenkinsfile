pipeline {
    agent any

    // Define environment variables
    environment {
        APP_VERSION = '1.0.0'
    }

    parameters {
        booleanParam(name: 'EXECUTE_TESTS', defaultValue: true, description: 'Should we execute tests?')
        string(name: 'DEPLOY_ENV', defaultValue: 'staging', description: 'Deployment environment (staging/production)')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building application...'
                echo "Using application version: ${APP_VERSION}"
                // Add your build commands here
            }
        }

        stage('Test') {
            when {
                expression { params.EXECUTE_TESTS }
            }
            steps {
                echo 'Running tests...'
                // Add your test commands here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                echo "Deploying to environment: ${params.DEPLOY_ENV}"
                // Add your deployment commands here
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed.'
        }
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
