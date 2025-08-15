pipeline {
    agent any
    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/aliparvej/Todo_List.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t todo-list .'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 8080:80 todo-list'
            }
        }
    }
}
