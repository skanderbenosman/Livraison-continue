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
        stage('Build') {
             steps{
                script{ 
                sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml "    
                }
           
            }
        }
        }
        }
