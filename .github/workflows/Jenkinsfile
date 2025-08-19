pipeline {
    agent any

    parameters {
        booleanParam(name: 'SKIP_TEST', defaultValue: false, description: 'Skip test stage if true')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'npm install' // Example build step
            }
        }

        stage('Test') {
            when {
                expression { return !params.SKIP_TEST }
            }
            steps {
                echo 'Running tests...'
                sh 'npm test'
            }
        }

        stage('Deploy') {
            when {
                allOf {
                    branch 'main'
                    expression { currentBuild.currentResult == 'SUCCESS' }
                }
            }
            steps {
                echo 'Deploying application...'
                // Example deploy command
                sh 'echo "App deployed successfully!"'
            }
        }
    }
}
