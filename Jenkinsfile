pipeline {
    agent any

    stages {

        stage('Git Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Arunasri-0096/Book-My-Show.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build || echo "No build step"'
            }
        }

        stage('Run App') {
            steps {
                sh 'nohup npm start &'
            }
        }

    }   // <-- closes stages

}       // <-- closes pipeline
