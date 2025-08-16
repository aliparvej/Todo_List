pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git url: 'https://github.com/aliparvej/Todo_List.git', branch: 'master'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'sudo docker build -t todo-list .'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'sudo docker run -d -p 8081:80 --name todo-container todo-list'
            }
        }
    }
}
