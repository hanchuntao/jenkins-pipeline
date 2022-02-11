pipeline {
    agent {label 'master'}

    stages {
        stage('Deploy') {
            steps {
                ansiblePlaybook(
                    playbook: "${env.WORKSPACE}/playbook.yml",
                    inventory: "${env.WORKSPACE}/hosts",
                    credentialsId: 'chhan-fedora35'
                )
            }
        }
    }
}
