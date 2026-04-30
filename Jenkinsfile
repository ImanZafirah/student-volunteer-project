pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/ImanZafirah/student-volunteer-project.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'echo "No tests implemented"'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t student-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8080:8080 student-app'
            }
        }
    }
}