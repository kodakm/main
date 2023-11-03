pipeline {
    agent any
    environment {
        // Set any environment variables you need
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                script {
                    def buildDir = 'build'
                    sh "mkdir -p $buildDir && cd $buildDir && cmake .. && make"
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    def buildDir = 'build'
                    sh "cd $buildDir && ctest"
                }
            }
        }
    }
}
