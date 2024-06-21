pipeline {
    agent any

    stages { 
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }
        
        stage('Start Application') {
            steps {
                bat 'npm start'
            }
        }
        
        stage('Run Tests') {
            steps {
                bat 'npm test'
            }
        }
    }
}