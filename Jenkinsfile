pipeline {
    agent { label 'jenkins_agent' }
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }
        stage('Run Flask App') {
            steps {
                sh 'python3 app.py > flask.log 2>&1 &'
                sleep 5
                sh 'curl -I http://127.0.0.1:5000 || exit 1'
            }
        }
    }

    triggers {
        pollSCM('H/5 * * * *')
        cron('0 * * * *')
    }
}
