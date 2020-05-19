@Library('test_jenkins@master') _
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
        stage('Test clone repo') {
            stage('Git Checkout') {
                gitcheckout(
                        branch: "master",
                        url: "https://github.com/YonathanGuez/Chrome_affiliateAmz.git"
                )
            }
        }
    }

}