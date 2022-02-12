pipeline {
    agent {
        docker {
            label 'docker'
            image 'quay.io/pelc/pelc2-ci'
        }
    }

    stages {
        stage('Build') {
            steps {
               sh '''
                   python --version
                   echo 'Hello Build!'
               '''
            }
        }
    }
}
