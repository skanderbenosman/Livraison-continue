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
        stage('push docker hub') {
             steps{
                script{
                    sh "ansible-playbook Ansible/docker-registry.yml -i Ansible/inventory/host.yml "
                }
            }
        }
        }
        }
