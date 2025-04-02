pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/yourusername/my-spring-app.git'
            }
        }

        stage('Build') {
            steps {
                sh './mvnw clean package'
            }
        }

        stage('Test') {
            steps {
                sh './mvnw test'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t my-spring-app:latest .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker run -d -p 8081:8080 my-spring-app:latest'
            }
        }
    }
}

