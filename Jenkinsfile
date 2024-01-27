pipeline {
    agent {
        docker {
            image 'manojreddy12/docker:v1.9'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages {
        stage('mvn version') {
            steps {
                script {
                    sh 'mvn --v'
                }
            }
        }
      stage('Build') {
            steps {
                // Execute your Maven commands within the Docker container
                sh 'mvn clean'
            }
        }
    }
}
