@Library('test_jenkins@master') _
pipeline {
    agent any
    parameters {
        string(name: 'BRANCH', defaultValue: 'master')
        string(name: 'REPOSITORY', defaultValue: 'selenium_jobs')
        string(name: 'MAVERIQ_VERSION', defaultValue: '')
    }
    stages {
        stage('Git Checkout') {
            steps {
                gitCheckout(
                        branch: "${params.master}",
                        url: "https://github.com/YonathanGuez/${params.REPOSITORY}.git"
                )
            }
        }
    }
}