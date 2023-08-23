pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from version control (e.g., Git)
                checkout scm
            }
        }
        
        stage('Build and Test') {
            steps {
                script {
                    // Build and test the Java project
                    sh "mvn clean install"
                }
            }
        }
        
        stage('Run Program') {
            steps {
                script {
                    // Run the compiled Java program
                    sh "java -cp target/classes com.jsc.Main"
                }
            }
        }
    }
}
