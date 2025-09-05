pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/meenakshiiyer2531/calculator-cicd.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install --upgrade pip'
                sh 'pip3 install -r requirements.txt || true'  // ignore if no requirements.txt
            }
        }

        stage('Run Tests') {
            steps {
                sh 'python3 -m unittest discover -s .'
            }
        }
    }
}
