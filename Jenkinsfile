pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Rutuja8093/jenkins-demo.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage (install dependencies)'
                sh 'pip install pytest || true'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests'
                sh 'pytest test_app.py'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application'
                sh './deploy.sh'
            }
        }
    }

    post {
        success {
            echo '✅ CI/CD Pipeline completed successfully'
        }
        failure {
            echo '❌ Pipeline failed'
        }
    }
}
