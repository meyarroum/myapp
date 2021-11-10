pipeline {

    agent any


        stages {
            stage ('Pull') {
                steps {
                    script{
                        checkout([$class: 'GitSCM', branches: [[name: '*/main']],
                            userRemoteConfigs: [[
                                credentialsID:'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',
                                url: 'https://github.com/meyarroum/myapp.git']]])
                       }
                
            }
        }
            stage ('Build') 
{
                steps {
                    script{
                    sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml "
                          }
                
                      }
        }		        
    }
	         
}
        
