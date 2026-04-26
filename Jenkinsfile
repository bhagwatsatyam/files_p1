pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-app .'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'pip install -r requirements.txt'
                bat 'python test_app.py'
            }
        }

        stage('Run App') {
            steps {
                bat 'docker run -d -p 5000:5000 my-app'
            }
        }
    }
}