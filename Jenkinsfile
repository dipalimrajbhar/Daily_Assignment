pipeline {
    agent any
 
    tools {
        maven 'maven3'    
        jdk 'JavaHome'       
    }
 
    stages {
        stage('Checkout') {
            steps {
               git branch: 'main', credentialsId: '721346f6-d8b7-4b6b-8fb5-e7187c1c5d8f', url: 'https://github.com/dipalimrajbhar/Daily_Assignment.git'
            }
        }
 
        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }
 
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
 
        stage('Package') {
            steps {
                bat 'mvn package'
            }
        }
 
        stage('Deploy to Test Environment') {
    steps {
        echo 'Deploying to test environment...'
    }
}
 
    }
 
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}