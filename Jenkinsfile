#!groovy
pipeline {
    agent any
    stages {
        stage('Run Test on different environment') {
            parallel{
                stage("Run Test on fedora35"){
                    agent {
                        node {
                            label "chhan-fedora35"
                        }
                    }
                    steps{
                        script{
                            echo "test on fedora35"
                        }
                    }
                }

                stage("Run Test on Ubuntu21.04"){
                    agent {
                        node{
                            label "ubuntu21.04"
                        }
                    }
                    steps{
                        script{
                            echo "test on ubuntu21.04"
                        }
                    }
                }
            }
        }
    }
}
