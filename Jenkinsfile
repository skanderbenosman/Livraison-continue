 pipeline {
  agent any
    stages {
        stage('Pull') {
             steps{
                script{
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                        userRemoteConfigs: [[
                            credentialsId: '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',
                            url: 'https://github.com/skanderbenosman/Livraison-continue.git']]])
                }
            }
        }
        stage('docker') {
             steps{
                script{
             sh "ansible-playbook Ansible/docker.yml -i Ansible/inventory/host.yml "
                }
            }
        }
        }
        }
