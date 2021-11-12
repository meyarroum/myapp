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
                    sh "ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml "
                          }
                
                      }
        }		        
    }
	         
}
        
