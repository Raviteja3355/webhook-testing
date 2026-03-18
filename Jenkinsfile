pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run') {
            steps {
                sh 'nohup python app.py &'
            }
        }
    }
}
