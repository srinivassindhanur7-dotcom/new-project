pipeline {
    agent any

    tools {
        maven 'Maven3'
        jdk 'JDK17'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                     url: 'https://github.com/srinivassindhanur7-dotcom/new-project.git'
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t new-project-app .'
            }
        }

        stage('Run') {
            steps {
                sh 'docker run -d -p 8080:8080 new-project-app'
            }
        }
    }
}
