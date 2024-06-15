pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from the repository
                git 'https://github.com/LyuboslavYotsov/Student-Registry-App-Jenkins-Exercise'
            }
        }
        
        
        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies
                sh '''
                npm install
                '''
            }
        }
        
        stage('Start Application') {
            steps {
                // Start the application (you can adjust this command as needed)
                sh '''
                npm start &
                '''
            }
        }
        
        stage('Run Tests') {
            steps {
                // Run the tests
                sh '''
                npm test
                '''
            }
        }
    }
}