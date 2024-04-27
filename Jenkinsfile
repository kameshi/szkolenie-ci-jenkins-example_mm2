pipeline {
    agent any
   tools {
        maven 'maven-3'
    }
    stages {
        stage('Clean') {
            steps {
               cleanWs()
            }
        }
        
        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/kameshi/szkolenie-ci-jenkins-example_mm2'
                sh 'mvn clean compile'
            }
        }
    }
}
