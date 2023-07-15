pipeline {
  agent any
    stages {
        stage('Pull') {
             steps{
                script{
                    checkout([$class: 'GitSCM', branches: [[name: '*/main']],
                        userRemoteConfigs: [[
                            credentialsId: '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',
                            url: 'https://github.com/mboudebous/MyappAngular.git']]])
                }
            }
        }
    }
}
