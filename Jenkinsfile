pipeline {
  agent any
    stages {
        stage('Pull') {
             steps{
                script{
                    checkout([$class: 'GitSCM', branches: [[name: '*/main']],
                        userRemoteConfigs: [[
                            credentialsId: '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',
                            url: 'https://github.com/mboudebous/myappan.git']]])
                }
            }
        }
    }
