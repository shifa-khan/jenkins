pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Compile the Java code
                sh 'echo "public class HelloWorld { public static void main(String[] args) { System.out.println(\\"Hello, world!\\"); } }" > HelloWorld.java'
                sh 'javac HelloWorld.java'
            }
        }
        stage('Run') {
            steps {
                // Run the compiled Java program
                sh 'java HelloWorld'
            }
        }
    }
}
