#!groovy
pipeline {
    agent any
    stages {
        stage('Read json data') {
            steps {
                script {
                    def props1 = readJSON text: '{ "key": "value" }'
                    assert props1['key'] == 'value'
                    assert props1.key == 'value'
                    echo "${props1}"

                    def props2 = readJSON text: '[ "a", "b"]'
                    assert props2[0] == 'a'
                    assert props2[1] == 'b'

                    def props3 = readJSON text: '{ "key": null, "a": "b" }', returnPojo: true
                    assert props3['key'] == null
                    props3.each { key, value ->
                        echo "Walked through key $key and value $value"
                    }
                }
            }
        }
    }
}
