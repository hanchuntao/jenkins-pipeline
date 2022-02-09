pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                withPythonEnv('/usr/bin/python') {
                    sh 'python --version'
                }
            }
        }
    }
}
