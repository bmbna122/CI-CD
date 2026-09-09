pipeline {
    agent any

    environment {
        IMAGE_NAME = "my-app"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME:$BUILD_NUMBER .'
            }
        }
        stage('Test') {
            steps {
                sh 'docker run --rm $IMAGE_NAME:$BUILD_NUMBER echo "tests would run here"'
            }
        }
    }
    post {
        always {
            echo "pipeline finished: ${currentBuild.currentResult}"
        }
    }
    }

    
  
         }
