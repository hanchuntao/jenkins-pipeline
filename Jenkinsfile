pipeline {
    agent {
        docker {
            label 'docker'
            image 'quay.io/pelc/pelc2-ci'
        }
    }

    environment {
        PELC_DATABASE_USER = 'postgres'
        PELC_DATABASE_PASSWORD = 'test'
        OCP_ADDRESS =  'https://api.ocp-c1.prod.psi.redhat.com:6443'
        CI_REGISTRY_IMAGE = 'quay.io/pelc/pelc2-ci'
        PELC_IMAGE = 'quay.io/pelc/pelc2'
        PELC_CI_USER = 'pelc+pelc_ci_cd'
        PELC_CI_PASSWORD = credentials('pelc_ci_cd_password')
    }

    stages {
//         stage('build-ci-image') {
//             steps {
//                 sh '''
//                     docker login -u=${PELC_CI_USER} -p=${PELC_CI_PASSWORD} quay.io
//
//                     # TO avoid image accumulate, auto delete after 14 days
//                     quay_expiration="14d";
//
//                     # https://docs.gitlab.com/ee/ci/docker/using_docker_build.html#docker-caching-example
//                     # image tag 'latest' cache image is from local
//                     docker build --cache-from ${CI_REGISTRY_IMAGE}:latest \
//                     --build-arg quay_expiration=${quay_expiration} \
//                     --tag ${CI_REGISTRY_IMAGE}:${CI_COMMIT_SHA} \
//                     --tag ${CI_REGISTRY_IMAGE}:latest -f docker-ci/Dockerfile .
//
//                     # docker push $CI_REGISTRY_IMAGE:$CI_COMMIT_SHA;
//                 '''
//             }
//         }
        stage('static-analysis-build') {
//             agent {
//                 docker {
//                     label 'docker'
//                     image 'quay.io/pelc/pelc2-ci'
//                 }
//             }
            failFast true
            parallel {
                stage('flake8'){
                    steps {
                        echo "flake8 test"
                       //sh "tox -e flake8 --current-env"
                    }
                }
                stage('pylint'){
                    steps {
                        echo "pylint test"
                        //sh "tox -e pylint --current-env"
                    }
                }
            }
        }
        stage('tests-it-promote') {
//             agent {
//                 docker {
//                     label 'docker'
//                     image 'quay.io/pelc/pelc2-ci'
//                 }
//             }
            failFast true
            parallel {
                stage('unit-tests'){
                    steps {
                        echo "unit-tests"
                        // sh "tox -e flake8 --current-env"
                    }
                }
            }
        }
        stage('deploy-to-dev') {
            steps{
                echo "deploy-to-deve"
            }
        }
    }
}
