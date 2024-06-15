pipeline {
    agent any

    environment {
        // Define the Node.js version you want to use
        NODE_VERSION = '20.x'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from the repository
                git 'https://github.com/LyuboslavYotsov/Student-Registry-App-Jenkins-Exercise'
            }
        }
        
        stage('Setup Node.js') {
            steps {
                // Install Node.js using NVM (Node Version Manager)
                sh '''
                curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
                export NVM_DIR="$HOME/.nvm"
                [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
                nvm install $NODE_VERSION
                nvm use $NODE_VERSION
                '''
            }
        }
        
        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies
                sh '''
                export NVM_DIR="$HOME/.nvm"
                [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
                nvm use $NODE_VERSION
                npm install
                '''
            }
        }
        
        stage('Start Application') {
            steps {
                // Start the application (you can adjust this command as needed)
                sh '''
                export NVM_DIR="$HOME/.nvm"
                [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
                nvm use $NODE_VERSION
                npm start &
                '''
            }
        }
        
        stage('Run Tests') {
            steps {
                // Run the tests
                sh '''
                export NVM_DIR="$HOME/.nvm"
                [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
                nvm use $NODE_VERSION
                npm test
                '''
            }
        }
    }

    post {
        always {
            // Archive the test results and other artifacts
            junit 'test-results.xml'
            archiveArtifacts artifacts: 'path/to/artifacts/**', allowEmptyArchive: true
        }

        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed.'
        }
    }
}