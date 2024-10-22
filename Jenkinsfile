pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/basyalsunil/daemonweb.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the website...'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                mkdir -p /var/www/html/daemonweb/
                cp -r * /var/www/html/daemonweb/
                '''
            }
        }
    }

    post {
        success {
            echo 'Deployment succeeded!'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
