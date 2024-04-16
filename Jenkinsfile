pipeline {
    agent any
    
    environment {
        JAVA_HOME = tool 'jdk17'
    }

    stages {
        stage('Git Checkout') {
            steps {
                git 'https://github.com/AjanSharma/demo-project.git'
            }
        }
        stage('Compile') {
            steps {
                withMaven(maven: 'maven3', jdk: 'jdk17'){
                    sh 'mvn compile'
                }
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Install') {
            steps {
                sh 'mvn install'
            }
        }
    }
}
