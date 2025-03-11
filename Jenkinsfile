pipeline {
    agent any

    environment {
        GIT_CREDENTIALS_ID = 'github-token' // Ensure this credential is added in Jenkins
        GIT_REPO = 'https://github.com/anasnaeem80/Jenkins-Powered-AI-ML-Model-Deployment-Pipeline.git'
        GIT_BRANCH = 'main'
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    try {
                        git credentialsId: GIT_CREDENTIALS_ID, branch: GIT_BRANCH, url: GIT_REPO
                    } catch (Exception e) {
                        echo "Git checkout failed: ${e.getMessage()}"
                        error("Stopping pipeline due to checkout failure")
                    }
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    echo 'Building the application...'
                    // Add actual build commands here, e.g., npm install, mvn package, etc.
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
                    // Add test execution commands here, e.g., pytest, jest, etc.
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying the application...'
                    // Add deployment logic, e.g., Docker push, Kubernetes deployment, etc.
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check logs for errors.'
        }
    }
}
