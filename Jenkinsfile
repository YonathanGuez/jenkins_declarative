@Library('test_jenkins@master') _
pipeline {
    agent any
    stages {
        stage('Clean workspace'){
            steps {
                cleanWs()
            }
        }
        stage("upload file") {
            steps{
                script{
                    def inputFile = input message: 'Upload file', parameters: [file(name: 'data.zip')]
                    new hudson.FilePath(new File("$workspace/data.zip")).copyFrom(inputFile)
                    inputFile.delete()
                }
            }
        }
        stage("checkout") {
            steps{
                echo fileExists('data.zip').toString()
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}