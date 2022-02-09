pipeline {
    agent any
    tools {
        go 'go1.17.6'
    }
    environment {
        GOPATH = "${env.WORKSPACE}"
    }
    stages {
        stage('Test') {
            steps {
                sh 'printenv'
                sh 'go version'
            }
        }
    }
}
