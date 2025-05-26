pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
            }
        }

        stage('Test') {
            steps {
                echo ' Running unit tests...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying to server...'
            }
        }
    }

    post {
        success {
            emailext (
                to: 'mksathish64@gmail.com',
                subject: "✅ SUCCESS: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Build ${env.JOB_NAME} #${env.BUILD_NUMBER} succeeded.\n\nCheck it here: ${env.BUILD_URL}"
            )
        }
        failure {
            emailext (
                to: 'mksathish64@gmail.com',
                subject: "❌ FAILURE: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Build ${env.JOB_NAME} #${env.BUILD_NUMBER} failed.\n\nCheck it here: ${env.BUILD_URL}"
            )
        }
    }
}
