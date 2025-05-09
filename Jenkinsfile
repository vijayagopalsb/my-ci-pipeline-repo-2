// Jenkinsfile (Declarative Pipeline)

pipeline {

    agent any

    stages {

        stage('Setup Python') {
            steps {
                bat 'python3 --version || python --version'
                bat 'python3 -m venv venv || python -m venv venv'
                bat '. venv/bin/activate && pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                bat '. venv/bin/activate && python -m unittest discover'
            }
        }

        stage('Build Success') {
            steps {
                echo 'Pipeline executed successfully!'
            }
        }
    }
}