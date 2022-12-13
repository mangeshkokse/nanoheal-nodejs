pipeline {
    agent any

    stages {
        stage('git pull') {
            steps {
                git branch: 'main', url: 'https://github.com/mangeshkokse/nanoheal-nodejs.git'
            }
        }
        stage('build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker build -t mangesh/nodeweb:${BUILD_NUMBER} .'
                sh 'docker images'
                sh 'docker run -d -p 8000:8080 mangesh/nodeweb:${BUILD_NUMBER}'
                sh 'docker ps'
            }
        }
    }
}
