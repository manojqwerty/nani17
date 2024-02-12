pipeline {
    agent any
        //docker {
            //image 'manojreddy12/maven:v1.0'
            //args '-v /var/run/docker.sock:/var/run/docker.sock'
        }//
    
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
         stage('Compile') {
            steps {
                // Execute your Maven commands within the Docker container
                sh 'mvn compile'
            }
        }
         stage('Test') {
            steps {
                // Execute your Maven commands within the Docker container
                sh 'mvn test'
            }
        }
         stage('Package') {
            steps {
                // Execute your Maven commands within the Docker container
                sh 'mvn package'
            }
        }
        stage('tomcat-deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://18.215.173.224:8085/')], contextPath: 'demo', war: ' "**/*.war"'
            }
        }
    }
}
