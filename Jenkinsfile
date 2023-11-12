pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout your code from version control (e.g., Git)
                checkout scm
            }
        }

        stage('Build and Test') {
            steps {
                // You can add any build and test steps here
            }
        }

        stage('Deploy with Docker Compose') {
            steps {
                // Run Docker Compose in the .devcontainer directory
                script {
                    def dockerComposeCommand = "docker-compose"
                    def dockerComposeFile = ".devcontainer/docker-compose.yml"

                    // Ensure Docker Compose is installed
                    sh "command -v ${dockerComposeCommand} >/dev/null || { echo 'Docker Compose is not installed.'; exit 1; }"

                    // Execute Docker Compose up command
                    sh "${dockerComposeCommand} -f ${dockerComposeFile} up -d"
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
