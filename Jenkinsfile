pipeline {
    agent any

    stages {
        stage('Build test') {
            steps {
                echo 'check hello'
            }
        }
        stage('Test 1') {
            steps {
               bat '''
                    echo "PATH=%PATH%"
               '''
            }
        }
        stage('Test 2') {
            steps {
                bat 'cd '
            }
        }
    }
}