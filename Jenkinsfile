pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout your source code from your version control system (e.g., Git)
                checkout scm
            }
        }
        
        stage('Build and Test') {
            steps {
                // Build your project. This example assumes Maven.
                sh 'gradlew build check'
                
                // Publish JUnit test results
                junit '**/target/test-classes/*.xml'
            }
        }
    }

    post {
        success {
            // You can add additional steps to run when the build is successful
            echo 'Build and tests were successful!'
        }
        failure {
            // You can add additional steps to run when the build fails
            echo 'Build or tests failed!'
        }
    }
}
