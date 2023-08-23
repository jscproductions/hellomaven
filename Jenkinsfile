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
                    // Define the Maven installation
                    def mvnHome = tool name: 'Apache Maven 3.9.4', type: 'maven'
                    env.PATH = "${mvnHome}/bin:${env.PATH}"

                    // Build and test the Java project
                    sh "${mvnHome}/bin/mvn clean install"
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
