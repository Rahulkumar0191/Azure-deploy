pipeline {
  agent any
  stages {
    stage('Main_Repo') {
      steps {
        sh 'echo "Hello"'
      }
    }
    stage ('Repo_checkout') {
      steps {
         checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Rahulkumar0191/Java_Test.git']]])
      }
    }  
      stage ('Build') {
      steps {
        sh '''cd /home/jenkins/workspace/Java_Test/CubeGenerator
              mvn clean test compile package'''
      }
    }
  }
}
