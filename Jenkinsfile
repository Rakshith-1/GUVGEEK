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

        stage('Run') {
            steps {
                // Run the Java program
                sh 'java GUV'
            }
        }
    }
}
