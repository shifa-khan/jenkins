pipeline {
    agent none
    stages {
        stage('Back-end') {
            agent {
                docker { 
                    image 'maven:3.8.1-adoptopenjdk-11' 
                    args '-u root' // Optional: Run Docker container as root
                }
            }
            steps {
                script {
                    sh 'mvn --version'
                    sh '''
                        echo "public class HelloWorld {
                            public static void main(String[] args) {
                                System.out.println(\\"Hello, World!\\");
                            }
                        }" > HelloWorld.java
                    '''
                    sh 'javac HelloWorld.java'
                    sh 'java HelloWorld'
                }
            }
        }
    }
}
