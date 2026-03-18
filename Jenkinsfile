pipeline {
    agent any

    stages {

        stage('Setup Python Environment') {
            steps {
                sh '''
                python3 -m venv venv
                . venv/bin/activate
                pip install --upgrade pip
                pip install -r requirements.txt
                '''
            }
        }

        stage('Run App') {
            steps {
                sh '''
                . venv/bin/activate
                nohup python app.py > app.log 2>&1 &
                '''
            }
        }
    }
}
