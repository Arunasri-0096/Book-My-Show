pipeline {
    agent any

    environment {
        IMAGE_NAME = "bookmyshow-app"
        CONTAINER_NAME = "bookmyshow-container"
    }

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

        stage('SonarQube Analysis') {
            steps {

                withSonarQubeEnv('SonarQube') {

                    sh '''
                    sonar-scanner \
                    -Dsonar.projectName=Book-My-Show \
                    -Dsonar.projectKey=Book-My-Show \
                    -Dsonar.sources=.
                    '''
                }
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build || echo "No build step"'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Docker Run') {
            steps {
                sh '''
                docker rm -f $CONTAINER_NAME || true

                docker run -d \
                --name $CONTAINER_NAME \
                -p 3000:3000 \
                $IMAGE_NAME
                '''
            }
        }

    }

}
