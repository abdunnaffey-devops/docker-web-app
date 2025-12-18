pipeline {
    agent {
        docker {
            image 'docker:24-cli'
            args '-u root -v /var/run/docker.sock:/var/run/docker.sock'
        }
    }

    environment {
        DOCKER_CONFIG = '/tmp/.docker'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/abdunnaffey-devops/docker-web-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t docker-web-app:jenkins .'
            }
        }
    }
}
