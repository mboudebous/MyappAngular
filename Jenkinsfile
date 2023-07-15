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
    
    stage('Build')
    {
        steps{
            script{
                sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
            }
        }
    }
    stage('Docker') {
             steps{
                script{
                    sh "sudo Ansible-playbook ansible/docker.yml -i Ansible/inventory/host.yml"
                }
            }
        }
}
}
