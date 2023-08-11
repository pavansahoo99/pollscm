pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from the Git repository
                checkout scm
            }
        }
        
        stage('Build and Test') {
            steps {
                // Run Maven clean and test goals or any other build steps
                echo 'mvn clean test'
            }
        }
        
        // Add more stages for deployment, notifications, etc.
    }
    
    post {
        success {
            echo 'Build and tests were successful!'
            // Add additional steps for deployment or notifications if needed
        }
        failure {
            echo 'Build or tests failed!'
            // Add additional steps for notifications or cleanup if needed
        }
    }
    
    triggers {
        pollSCM('H/5 * * * *') // Poll every 5 minutes (adjust the schedule as needed)
    }
}
