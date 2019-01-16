pipeline {
    agent any
    
    stages {
       stage('Check-in') {
         steps {
            checkout scm
            sh 'docker build -t 133506877714.dkr.ecr.eu-west-1.amazonaws.com/pronto-dashboard:stable .'
            withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', credentialsId: 'thor-chick']]) {
                sh 'docker push 133506877714.dkr.ecr.eu-west-1.amazonaws.com/pronto-dashboard:stable'
            }

         }
       }

    }
}

