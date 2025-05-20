pipeline {
    agent any

    stages {
        stage('Declarative: Checkout SCM') {
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
                // Copie le fichier index.html dans le dossier web avec sudo sans mot de passe
                sh 'sudo /bin/cp index.html /Library/WebServer/Documents/index.html'
            }
        }

        stage('Redémarrer Apache2') {
            steps {
                // Redémarre Apache avec apachectl (macOS)
                sh 'sudo /usr/sbin/apachectl restart'
            }
        }
    }

    post {
        failure {
            echo 'Une erreur est survenue pendant le déploiement.'
        }
    }
}
