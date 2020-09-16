pipeline {
  agent any
    tools {
        maven 'Maven3.3.9'
        jdk 'jdk8'
    }
  stages {

    stage('Build') {
      steps {
        bat 'mvn clean install'
      }
    }
    stage('Report') {
      steps {
        junit(testResults: 'target/surefire-reports/**/*.xml')
        archiveArtifacts 'target/*.jar,target/*.hpi'
      }
    }
  }
}
