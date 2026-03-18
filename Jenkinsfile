pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }

        stage('Run') {
            steps {
                bat 'java -jar target/app.jar'
            }
        }
    }
}
