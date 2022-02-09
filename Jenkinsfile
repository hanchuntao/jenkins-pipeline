pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                script {
                    writeFile(file: "base64File", text: "amVua2lucyBib29r", encoding: "Base64")
                    def content = readFile(file: "base64File", encoding: 'UTF-8')
                    echo "${content}"
                }
            }
        }
    }
}