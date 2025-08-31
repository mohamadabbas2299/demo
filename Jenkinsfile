pipeline {
    agent any
    tools {
        jdk 'Java 17'
        maven 'Maven 3.9.0'   // Or 'Maven 3.9.0' if you named it like that
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
