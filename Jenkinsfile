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
   stage('Install') {
             steps{
                script{
                    sh "npm install"
                }
            }
        } 
    stage('Build')
    {
        steps{
            script{
                sh "ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml"
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
