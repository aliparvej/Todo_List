pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/aliparvej/Todo_List.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh '''
                cd Todo_List
                docker build -t todo-list .
                '''
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f todo-container || true
                docker run -d -p 8081:80 --name todo-container todo-list
                '''
            }
        }
    }
}
