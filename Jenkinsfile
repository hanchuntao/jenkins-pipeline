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
            echo "pipeline post always"
            cleanWs()
        }
    }
}
