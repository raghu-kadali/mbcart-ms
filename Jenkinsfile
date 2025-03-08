pipeline {
    agent any  // Run on any available agent

    environment {
        SONARQUBE_SERVER = 'sonar'  // Name of the SonarQube server in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from Git repository
                git 'https://github.com/yourusername/your-repo.git'
            }
        }

        stage('Build') {
            steps {
                // Build the project (e.g., using Maven)
                echo 'Building the project...'
                sh 'mvn clean install'  // Replace with your build tool (e.g., Maven, Gradle)
            }
        }

        stage('SonarQube Analysis') {
            steps {
                // Run SonarQube analysis
                script {
                    // Execute SonarQube scan
                    sh "mvn sonar:sonar -Dsonar.projectKey=my_project_key -Dsonar.host.url=http://$SONARQUBE_SERVER:9000 -Dsonar.login=your_sonarqube_token"
                }
            }
        }

        stage('Deploy') {
            steps {
                // Deploy the project (replace with your actual deployment command)
                echo 'Deploying the project...'
                sh './deploy.sh'  // Example deploy script
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
