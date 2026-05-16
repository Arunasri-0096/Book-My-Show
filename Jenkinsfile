pipeline {
    agent any

    tools {
        nodejs 'node18. stage('Git Checkout') {
  pipeline {
    agent any

    tools {
        nodejs 'node18. stage('Git Checkout') {
   stage('Git Checkout') {
    steps {
        git branch: 'main',
        url: 'https://github.com/Arunasri-0096/Book-My-Show.git'
    }
}
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t bms-app .'
            }
        }

        stage('Docker Run') {
            steps {
                sh '''
                docker stop bms-container || true
                docker rm bms-container || true
                docker run -d -p 3000:3000 --name bms-container bms-app
                '''
            }
        }
    }
 stage('Git Checkout') {
    steps {
        git branch: 'main',
        url: 'https://github.com/Arunasri-0096/Book-My-Show.git'
    }
}
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t bms-app .'
            }
        }

        stage('Docker Run') {
            steps {
                sh '''
                docker stop bms-container || true
                docker rm bms-container || true
                docker run -d -p 3000:3000 --name bms-container bms-app
                '''
            }
        }
    }
}
