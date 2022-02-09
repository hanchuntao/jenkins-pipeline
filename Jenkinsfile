pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Running ${env.BUILD_NUMBER} ON ${env.JENKINS_URL}"
                echo "${env.GIT_BRANCH}"
                sh 'printenv'
                sh script: 'printenv', returnStatus: true
            }
        }
    }
}
