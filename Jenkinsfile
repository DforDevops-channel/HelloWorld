pipeline {
    agent any
    
 
    tools {
        maven 'maven399'
    }
                

    stages {
        stage('Hello') {
           
            steps {
                echo 'Hello World'
            }
        }
        stage('Maven Version') {
            
            steps {
                sh '''
                    mvn --version
            '''    
            }
        }
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/DforDevops-channel/HelloWorld.git'
            }
        }
        stage('Build') {
            steps {
                sh '''
                    mvn clean package
                '''    
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                    java -jar target/*.jar
            '''
            }
        }
    }
}
