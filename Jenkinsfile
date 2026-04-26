pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/bhagwatsatyam/files_p1.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-app .'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pip install -r requirements.txt'
                sh 'python test_app.py'
            }
        }

        stage('Run App') {
            steps {
                sh 'docker run -d -p 5000:5000 my-app'
            }
        }
    }
}