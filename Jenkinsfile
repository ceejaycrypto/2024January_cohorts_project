pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh 'cd SampleWebApp mvn test'
            }
        }
        stage('Build & Complie') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }
        
        stage('Deploy to Tomcat Web Server') {
            steps {
             deploy adapters: [tomcat9(credentialsId: 'Deploytomcat', path: '', url: 'http://18.209.112.1:8080/')], contextPath: 'webapp', war: '**/*.war'
            }
        }
    }
}
