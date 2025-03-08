pipeline {
    agent any  // Run the pipeline on any available agent

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from your Git repository
                git 'https://github.com/yourusername/your-repo.git'
            }
        }

        stage('Build') {
            steps {
                // A simple build step (for example, a Java build with Maven)
                echo 'Building the project...'
                sh 'mvn clean install'  // For a Maven-based Java project
            }
        }

        stage('Test') {
            steps {
                // Run tests (example for a Java project)
                echo 'Running tests...'
                sh 'mvn test'  // For a Maven-based Java project
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }

        failure {
            echo 'Pipeline failed. Please check the logs.'
        }
    }
}
