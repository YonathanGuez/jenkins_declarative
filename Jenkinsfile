@Library('test_jenkins@master') _
pipeline {
    agent any
    stages {
        stage('Build test') {
            steps {
                echo 'check hello'
            }
        }
        stage('Test 1: Print all Path on windows') {
            steps {
               bat '''
                    echo "PATH=%PATH%"
               '''
            }
        }
        stage('Test 2: go to the root ') {
            steps {
                bat 'cd '
            }
        }
    }
}