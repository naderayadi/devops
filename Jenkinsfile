pipeline {
    agent any

    tools {
        // Nom exact de l'installation Maven dans : Manage Jenkins > Tools > Maven installations
        maven 'Maven'
    }

    triggers {
        // Declenchement automatique par le webhook GitHub (etape 7)
        githubPush()
    }

    stages {
        stage('Checkout Git') {
            steps {
                // Remplacer ID_DU_CREDENTIAL par l'ID visible dans Manage Jenkins > Credentials
                git branch: 'main',
                    credentialsId: 'ID_DU_CREDENTIAL',
                    url: 'https://github.com/naderayadi/devops.git'
            }
        }

        stage('Build Maven') {
            steps {
                // Le pom.xml est dans le dossier backend
                dir('backend') {
                    sh 'mvn -B compile'
                }
            }
        }
    }
}
