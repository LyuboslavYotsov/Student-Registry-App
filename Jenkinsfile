pipeline {
    agent any

    stages { 
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('NPM Audit Check') {
            steps {
                bat 'npm audit'
            }
        }
        
        stage('Run Integration Tests') {
            steps {
                bat 'npm test'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Fake deploying'
            }
        }
    }
}