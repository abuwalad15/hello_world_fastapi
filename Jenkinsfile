pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/kamu-user/hello_world_fastapi.git'
            }
        }

        stage('Build Docker Images') {
            steps {
                script {
                    sh 'docker-compose build'
                }
            }
        }

        stage('Run Containers') {
            steps {
                script {
                    sh 'docker-compose up -d'
                }
            }
        }
    }
}
