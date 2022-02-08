pipeline {
    agent none

    stages {
        stage('stash') {
            agent { label "master"}
            steps {
                writeFile file: "a.txt", text: "$BUILD_NUMBER"
                stash(name: "abc", includes: "a.txt")
            }
        }

        stage('unstash') {
            agent { label "chhan-fedora35"}
            steps {
                script {
                    unstash("abc")
                    def content = readFile("a.txt")
                    echo "${content}"
                }
            }
        }
    }
}
