
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'python3 -m py_compile app.py'
            }
        }

        stage('Test') {
            steps {
                echo 'Running automated tests...'
                sh 'python3 -m unittest test_app.py'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh '''
                    mkdir -p deploy
                    cp app.py deploy/app.py
                '''
            }
        }
    }

    post {
        success {
            echo 'CI/CD pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check Console Output.'
        }
    }
}
