// Jenkinsfile (Declarative Pipeline)

pipeline {
    agent any

    tools {
        python 'Python-3.12.5' // Make sure this is configured in Jenkins tools
    }

    stages {
        stage("Clone") {
            steps {
                git 'https://github.com/vijayagopalsb/my-ci-pipeline-repo-2.git'
            }
        }

         stage('Install Dependencies') {
            steps {
                sh 'python -m venv venv'
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