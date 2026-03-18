pipeline {
    agent any

    stages {

        stage('Stop Old App') {
            steps {
                sh 'pkill -f app.py || true'
            }
        }

        stage('Install Dependencies') {
            steps {
                dir('backend') {
                    sh '''
                    python3 -m venv venv
                    venv/bin/pip install --upgrade pip
                    venv/bin/pip install -r requirements.txt
                    '''
                }
            }
        }

        stage('Run App') {
            steps {
                dir('backend') {
                    sh '''
                    nohup venv/bin/python app.py > app.log 2>&1 &
                    '''
                }
            }
        }
    }
}
