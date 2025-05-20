pipeline {
    agent any

    stages {
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
        success {
            echo 'Déploiement HTML effectué et Apache redémarré.'
        }
        failure {
            echo 'Une erreur est survenue pendant le déploiement.'
        }
    }
}

 
