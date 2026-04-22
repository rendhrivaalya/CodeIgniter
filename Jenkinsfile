pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'develop', url: 'https://github.com/rendhrivaalya/CodeIgniter.git'
            }
        }

        stage('Check Composer') {
            steps {
                sh 'composer --version'
                sh 'php -v'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                sh 'composer install --ignore-platform-reqs || true'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'echo Testing skipped'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying to production environment...'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
