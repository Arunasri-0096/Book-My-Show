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
                sh 'npm run build || echo "No build step found"'
            }
        }

        stage('Run Application') {
            steps {
                sh 'nohup npm start &'
            }
        }
    }
}
