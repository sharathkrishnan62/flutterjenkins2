pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                bat 'flutter pub get'
            }
        }

        stage('Analyze') {
            steps {
                bat 'flutter analyze'
            }
        }

        stage('Test') {
            steps {
                bat 'flutter test'
            }
        }

        stage('Build Web') {
            steps {
                bat 'flutter build web --release'
            }
        }

        stage('Archive Web') {
            steps {
                archiveArtifacts artifacts: 'build\\web\\**',
                                  fingerprint: true
            }
        }
    }
}