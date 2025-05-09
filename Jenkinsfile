// Jenkinsfile (Declarative Pipeline)

pipeline {

    agent any

    stages {

        stage('Setup Python') {
            steps {
                bat '''
                python --version
                python -m venv venv
                call venv\\Scripts\\activate.bat && pip install -r requirements.txt
                '''
            }
        }

        stage('Run Tests') {
            steps {
                bat '''
                call venv\\Scripts\\activate.bat && python -m unittest discover
                '''
            }
        }

        stage('Build Success') {
            steps {
                echo 'Pipeline executed successfully!'
            }
        }
    }
}