pipeline {
    agent any
    stages {
                stage('Install requirements') {
            steps {
                sh 'PATH=$PATH:/home/jenkins/.local/bin ansible-galaxy install -r requirements.yml'
            }
        }
        stage('Run molecule') {
            steps {
                sh 'PATH=$PATH:/home/jenkins/.local/bin molecule test'
            }
        }
        stage('Clean role') {
            steps {
                sh 'PATH=$PATH:/home/jenkins/.local/bin ansible-galaxy role remove vector-role'
            }
        }
    }
}
