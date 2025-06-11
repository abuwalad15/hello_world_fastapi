pipeline {
    agent any

    stages {
        stage('Info') {
            steps {
                sh 'git branch'
                sh 'git rev-parse --abbrev-ref HEAD'
            }
        }
        stage('Clone Repo') {
            steps {
                deleteDir() // hapus workspace lama
                git credentialsId: 'b9fcb1d0-bf45-4f86-b028-b4f2318be11b', branch: 'main', url: 'https://github.com/abuwalad15/hello_world_fastapi.git'
            }
        }

        stage('Build Docker Images') {
            steps {
                sh 'docker-compose build'
            }
        }

        stage('Run Containers') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}
