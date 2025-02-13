pipeline {
    agent any

    environment {
        JAVA_HOME = '/usr/lib/jvm/java-17-openjdk'  // Define the Java version to use
        PATH = "$JAVA_HOME/bin:$PATH"  // Ensure Java binaries are on the PATH
    }

    stages {
        stage('build') {
            steps {
                // Check out the code from the Git repository
                git 'https://github.com/SanthoshkumaraGV/simplejava.git'  // Replace with your repo URL
            }
        }

        stage('Compile') {
            steps {
                // Compile the Java program using javac
                script {
                    sh 'javac simple.java'  // Compiling the HelloWorld.java file
                }
            }
        }

        stage('Package') {
            steps {
                // Package the compiled classes into a JAR file using jar
                script {
                    sh 'jar cf simple.jar simple.class'  // Create the JAR file
                }
            }
        }

        stage('Run JAR') {
            steps {
                // Run the generated JAR file
                script {
                    sh 'java -jar simple.jar'  // Run the JAR file
                }
            }
        }

        stage('Archive JAR') {
            steps {
                // Archive the JAR file
                archiveArtifacts artifacts: 'simple.jar', allowEmptyArchive: true
            }
        }
    }

    post {
        success {
            echo 'Build and execution succeeded!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
