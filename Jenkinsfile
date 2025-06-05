pipeline {
    agent any

    environment {
        DOCKER_COMPOSE_PATH = '/usr/local/bin/docker-compose'
    }

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/purna-muddangula/Three-tier-Application-Deployment-.git'
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

    post {
        success {
            echo 'Deployment successful!'
        }
