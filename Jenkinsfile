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
