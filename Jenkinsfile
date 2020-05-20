@Library('test_jenkins@master') _
pipeline {
    agent any
    parameters {
        string(name: 'BRANCH', defaultValue: 'master')
        string(name: 'REPOSITORY', defaultValue: 'selenium_jobs')
    }
    stages {
        stage('Clean workspace'){
            steps {
                cleanWs()
            }
        }
        stage('Print Param') {
            steps {
                echo params.BRANCH
                echo params.REPOSITORY
            }
        }
        stage('Git Checkout') {
            steps {
                gitCheckout(
                        branch: "${params.BRANCH}",
                        url: "https://github.com/YonathanGuez/${params.REPOSITORY}.git"
                )
            }
        }

    }
    post {
        always {
            cleanWs()
        }
    }
}