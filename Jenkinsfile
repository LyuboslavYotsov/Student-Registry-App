pipeline {
    agent any

    stages {
        stage('Checkout repo') {
            steps {
                git 'https://github.com/LyuboslavYotsov/Student-Registry-App-Jenkins-Exercise'
            }
        }

        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }
        
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
    }
}