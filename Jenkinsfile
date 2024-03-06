pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Compile the .cpp file using shell script
                    sh 'g++ -o executable PES1UG21CS563.cpp'
                }
                echo 'Build Stage Successful'
            }
        }
        
        stage('Test') {
            steps {
                script {
                    // Print output of .cpp file using shell script
                    sh './executable'
                }
                echo 'Test Stage Successful'
            }
        }
        
        stage('Deploy') {
            steps {
                // Deployment steps if any
                echo 'Deployment Successful'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
