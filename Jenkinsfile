pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code from GitHub'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building MedCart HTML project...'
                bat '''
                    if not exist build mkdir build
                    copy index.html build\\
                '''
            }
        }

        stage('Archive') {
            steps {
                echo 'Archiving build artifacts'
                archiveArtifacts artifacts: 'build/**', fingerprint: true
            }
        }
    }
}
