// Jenkinsfile (Declarative Pipeline)

pipeline {

    agent any

    stages {

        stage('Setup Python') {
            steps {
                sh 'python3 --version || python --version'
                sh 'python3 -m venv venv || python -m venv venv'
                sh '. venv/bin/activate && pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh '. venv/bin/activate && python -m unittest discover'
            }
        }

        stage('Build Success') {
            steps {
                echo 'Pipeline executed successfully!'
            }
        }
    }
}