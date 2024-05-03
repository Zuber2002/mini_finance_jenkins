pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Zuber2002/mini_finance_jenkins.git', branch: 'master'
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // If your build requires specific tools, use a container or node setup
                    sh 'npm install'
                }
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test' // Assuming you have a test script in your package.json
            }
        }

       
    }

    post {
        
        success {
            echo 'Pipeline succeeded'
        }

        failure {
            echo 'Pipeline failed'
        }
    }
}
