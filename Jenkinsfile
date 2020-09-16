pipeline {
    agent any
    tools {
        maven 'maven3.6.3'
        jdk 'JDK9'
    }
    stages {
            stage ('Build') {
            steps {
                bat 'mvn -Dmaven.test.failure.ignore=true install' 
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
    }
}
