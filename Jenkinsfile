pipeline {
    agent { label 'jenkins_agent' }
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'python3 --version'
                sh 'pip --version'
                sh 'flask --version'
            }
        }
        stage('Run Flask App') {
            steps {
                sh 'python3 app.py > flask.log 2>&1 &'
                sleep 5
                sh 'cat flask.log'
                sh '....Flask App was Run....'
            }
        }
    }
}
