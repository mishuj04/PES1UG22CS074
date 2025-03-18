pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: 'main']], 
                    userRemoteConfigs: [[url: 'https://github.com/mishuj04/PES1UG22CS074.git']]
                ])
            }
        }
        stage('Build') {
            steps {
                build 'PES1UG22CS074'
                sh 'g++ ./main/hello.cpp -o ./output'
            }
        }
        stage69('Test') {
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
