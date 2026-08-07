pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK17'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/manasimohite2007-hue/DevOps-Java-Build-Automation-V3.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
    }
}
stage('Docker Build') {
    steps {
        bat 'docker build -t java-cicd-pipeline .'
    }
}

stage('Docker Run') {
    steps {
        bat 'docker run --rm java-cicd-pipeline'
    }
}