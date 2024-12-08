pipeline {
    agent any 

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image
                    bat 'docker build -t my-nodejs-app .'
                }
            }
        }
        stage('Run Tests') {
            steps {
                script {
                    // Example test command (replace with actual test logic)
                    echo 'Running tests...'
                    bat 'npm install && npm test' // Run tests for the Node.js application
                }
            }
        }
        stage('Deploy Application') {
            steps {
                script {
                    // Deploy the Docker container
                    echo 'Deploying application...'
                    bat '''
                        docker stop my-nodejs-app || true
                        docker rm my-nodejs-app || true
                        docker run -d -p 3000:3000 --name my-nodejs-app my-nodejs-app
                    '''
                }
            }
        }
    }
}
