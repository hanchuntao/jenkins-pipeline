pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Hello world'
            }
        }
    }

    post {
        always {
            mail body: 'test email function', from: 'chhan@redhat.com', subject: 'Build status', to: 'chhan'
        }
    }
}
