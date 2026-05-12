pipeline {
    agent any
    tools {
        maven 'Maven'
        jdk 'jdk'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch:'main', url:'https://github.com/Priyanshu-Madhup/program6.git'
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
    }
}
