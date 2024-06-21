pipeline {
    agent {
        docker {
            image 'my-node-agent'
            args '-p 3000:3000'
        }
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/s24580/kolos-devops-26-.06.git', branch: 'main'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Lint') {
            steps {
                sh 'npm run lint'
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
