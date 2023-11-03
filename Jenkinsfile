pipeline {
    agent any

    environment {
        SOURCE_CODE_PATH = '/home/azureuser/mahesh/main'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh "mkdir -p ${SOURCE_CODE_PATH}/build"
                dir("${SOURCE_CODE_PATH}/build") {
                    sh "cd ${SOURCE_CODE_PATH}/build && cmake ."
                    sh "cd ${SOURCE_CODE_PATH}/build && make"
                }
            }
        }
    }
}

