pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Check User') {
            steps {
                sh 'whoami'
            }
        }
        stage('Copier index.html') {
            steps {
                sh 'sudo cp index.html /Library/WebServer/Documents/index.html'
            }
        }
        stage('Redémarrer Apache2') {
            steps {
                sh 'sudo apachectl restart'
            }
        }
    }
    post {
        failure {
            echo 'Une erreur est survenue pendant le déploiement.'
        }
    }
}


 
