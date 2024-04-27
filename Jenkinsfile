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
                git branch: 'main', url: 'https://github.com/spring-projects/spring-petclinic'
                sh 'mvn clean verify'
                slackSend color: "good", message: "Message from Jenkins Pipelin Marek Madeła"
            }
        }
    }
    
    post {
        always {
            junit allowEmptyResults: true, testResults: '**/target/surefire-reports/*.xml'
        }
    }
}
