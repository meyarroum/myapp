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
        
