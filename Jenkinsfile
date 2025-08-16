pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'master', url: 'https://github.com/aliparvej/Todo_List.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t todo-list .'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh '''
                docker rm -f todo-container || true
                docker run -d -p 8080:8080 --name todo-container todo-list
                '''
            }
        }
    }
}
