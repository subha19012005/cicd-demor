pipeline {

    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Building the application...'
                bat 'python -m py_compile app.py'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'python -m unittest test_app.py'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                bat 'if not exist deploy mkdir deploy'
                bat 'copy app.py deploy\\app.py'
            }
        }
    }
}