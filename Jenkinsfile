pipeline {
    agent {
        label 'jenkins-slave-label'
    }
    
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
    }
}
