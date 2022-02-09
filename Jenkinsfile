pipeline {
    agent any

    stages {
        stage('Build with jdk-9.0.4') {
            tools {
                jdk "jdk-9.0.4"
            }
            steps {
                sh "printenv"
            }
        }
        stage('Build with jdk-9.0.1') {
            tools {
                jdk "jdk-9.0.1"
            }
            steps {
                sh "printenv"
            }
        }
    }
}
