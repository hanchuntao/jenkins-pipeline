pipeline {
    agent any

    stages {
        stage('init') {
              steps {
                script{
                  def dockerPath = tool name: 'docker', type: 'dockerTool' //全局配置里的docker
                  echo "${dockerPath}"
                  env.PATH = "${dockerPath}/bin:${env.PATH}" //添加了系统环境变量上
                }
              }
        }

        stage('Build') {
            steps {
                script{
                  sh "docker --version"
                }
            }
        }
   }
}