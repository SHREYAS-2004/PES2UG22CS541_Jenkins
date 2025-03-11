pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/SHREYAS-2004/PES2UG22CS541_Jenkins.git']]
                ])
                 
            }
        }

        stage('Build') {
            steps {
                // sh 'g++ main/hello.cpp -o main/output'
                echo 'Building...'
                sh 'exit 1'
            }
        }

        stage('Test') {
            steps {
                sh './main/output'
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