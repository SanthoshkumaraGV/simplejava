// Jenkinsfile
pipeline {
    agent any

    environment {
        JAVA_HOME = '/usr/lib/jvm/java-11-openjdk'  // Define Java version to use (adjust as necessary)
        PATH = "$JAVA_HOME/bin:$PATH"
    }

    stages {
        stage('Checkout') {
            steps {
                // Check out the code from your repository
                git 'https://github.com/SanthoshkumaraGV/simplejava.git'  // Replace with your repo URL
            }
        }

        stage('Compile') {
            steps {
                // Compile the Java program
                script {
                    sh 'javac simple.java'  // Compile the Java program using javac
                }
            }
        }

        stage('Run') {
            steps {
                // Run the compiled Java program
                script {
                    sh 'java simple'  // Run the program using java command
                }
            }
        }
    }

    post {
        success {
            echo 'Build and execution succeeded!'
        }
        failure {
            echo 'Build or execution failed.'
        }
    }
}
