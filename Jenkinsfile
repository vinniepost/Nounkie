pipeline {
    agent any

    stages {
        stage('Deploy with Docker Compose') {
            steps {
                script {
                    // Ensure Docker Compose is installed
                    sh "command -v docker-compose >/dev/null || { echo 'Docker Compose is not installed.'; exit 1; }"

                    // Execute Docker Compose up command
                    sh "docker-compose -f .devcontainer/docker-compose.yml up -d"
                }
            }
        }
    }

    post {
        success {
            // Any steps to perform after a successful build
        }
        failure {
            // Any steps to perform after a failed build
        }
    }
}
