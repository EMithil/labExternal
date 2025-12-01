pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('List Files') {
            steps {
                echo "Workspace files:"
                bat "dir"
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'index.html', fingerprint: true
            }
        }
    }

    post {
        success {
            echo "Build complete"
        }
    }
}
