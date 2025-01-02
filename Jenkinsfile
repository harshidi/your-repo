pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/harshidi/your-repo.git'
            }
        }
        stage('Build') {
            steps {
                script {
                    docker.build('pedantic_perlman
                }
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Push to IBM Cloud Container Registry') {
            steps {
                script {
                    docker.withRegistry('https://us.icr.io', 'IBM_CLOUD_API_KEY') {
                        docker.image('pedantic_perlman').push('latest')
                    }
                }
            }
        }
        stage('Deploy') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
            }
        }
    }
}
