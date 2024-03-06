pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '**/main']],
                          userRemoteConfigs: [[url: 'https://github.com/shravanihm/PES1UG21CS563_Jenkins.git']]])
            }
        }
        stage('Build') {
            steps {
                build 'PES1UG21CS563-1'
                sh 'g++ PES1UG21CS563.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
