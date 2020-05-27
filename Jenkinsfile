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
        stage("upload") {
            script{
                def inputFile = input message: 'Upload file', parameters: [file(name: 'data.zip')]
                new hudson.FilePath(new File("$workspace/data.zip")).copyFrom(inputFile)
                inputFile.delete()
            }
        }
        stage("checkout") {
            script{
                echo fileExists('data.zip').toString()
            }
        }
//        stage('Print all files') {
//            steps {
////                echo params.BRANCH
////                echo params.REPOSITORY
//                bat 'dir'
//            }
//        }
//        stage('Git Checkout') {
//            steps {
//                gitCheckout(
//                        branch: "${params.BRANCH}",
//                        url: "https://github.com/YonathanGuez/${params.REPOSITORY}.git"
//                )
//            }
//        }

    }
    post {
        always {
            cleanWs()
        }
    }
}