pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Create a directory to store Java source code
                    dir('java') {
                        // Define the Java source code
                        writeFile file: 'HelloWorld.java', text: '''
                            public class HelloWorld {
                                public static void main(String[] args) {
                                    System.out.println("Hello, world!");
                                }
                            }
                        '''
                        
                        // Compile the Java source code
                        sh 'javac HelloWorld.java'
                    }
                }
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
