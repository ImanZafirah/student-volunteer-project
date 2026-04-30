pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                // Jenkins handles the git command natively, so this stays the same
                git 'https://github.com/ImanZafirah/student-volunteer-project.git'
            }
        }

        stage('Build') {
            steps {
                // Changed sh to bat for Windows CMD
                bat 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                // Changed sh to bat
                bat 'echo "No tests implemented"'
            }
        }

        stage('Docker Build') {
            steps {
                // Changed sh to bat
                bat 'docker build -t student-app .'
            }
        }

        stage('Run Container') {
            steps {
                /* 
                   Changed sh to bat.
                   Modified host port to 9090.
                   Added --name for easier management later.
                */
                bat 'docker run -d --name student-container -p 9090:8080 student-app'
            }
        }
    }
}