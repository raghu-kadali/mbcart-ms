pipeline {
    agent any
    stages {
        stage ('Build') {
            step {
                echo "*********Building the application*********"
                sh 'mvn package'
            }
        }
        stage ('sonar') {
            steps {
                 echo "*********Building the sonar*********"
            }
        }
        stage ('Docker') {
            steps {
                echo "*******Builld the docker appliaction"
            }

        }
        stage ('k8s') {
            steps {
                echo "******Building the k8"
            }
        }
    }
}
