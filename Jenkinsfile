pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from the Git repository
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                // Compile the Java source code
                sh 'javac GUV.java'
            }
        }

        stage('Build Docker Image') {
            steps {
                // Build the Docker image
                script {
                    def image = docker.build('GUV:latest', '.')
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                // Run the Docker container
                script {
                    def app = docker.image('GUV:latest')
                    app.inside {
                        sh 'java -jar GUV.jar' // Assuming your Java app is packaged as a JAR file
                    }
                }
            }
        }
    }
}
