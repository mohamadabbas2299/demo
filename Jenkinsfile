pipeline {
    agent any
    tools {
        jdk 'Java 17'
        maven 'Maven 3.9.0'   // Or 'Maven 3.9.0' if you named it like that
    }
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/mohamadabbas2299/demo.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t springboot-app .'
            }
        }

        stage('Docker Run') {
            steps {
                // Stop any old container and start new
                sh '''
                  docker stop springboot-app || true
                  docker rm springboot-app || true
                  docker run -d -p 8080:8080 --name springboot-app springboot-app
                '''
            }
        }
        stage('Docker Build') {
    steps {
        sh 'docker build -t springboot-app .'
        sh 'docker run -d -p 8081:8080 springboot-app'
    }
}
    }
}
