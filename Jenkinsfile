pipeline {
    agent any

    stages {

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
