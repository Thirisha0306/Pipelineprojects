pipeline {
    agent any
    stages{
        stage('checkout') {
            steps{
                git branch: 'main', url: 'https://github.com/Thirisha0306/Pipelineprojects.git'

            }
        }
        stage('Install Dependecies'){
            steps{
                bat 'pip install -r requirements.txt'
            }
        }
        stage('Run Unit Tests'){
            steps {
                bat 'pytest test_app.py'
            }
        }
    }
}