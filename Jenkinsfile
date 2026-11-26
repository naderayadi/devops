pipeline {
    agent any

    stages {
        stage('Checkout Git') {
            steps {
                // Recupere le code depuis le repo GitHub configure dans le job
                // (URL https://github.com/naderayadi/devops + credentials "nader")
                checkout scm
            }
        }

        stage('Build Maven') {
            steps {
                // Le pom.xml est dans le dossier backend
                dir('backend') {
                    sh 'chmod +x mvnw'
                    sh './mvnw -B compile'
                }
            }
        }
    }
}
