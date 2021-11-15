pipeline {

    agent any


    stages {


       stage ('Pull') {
            steps {
               script {
               checkout([$class: 'GitSCM', branches: [[name: '*/main']],
                userRemoteConfigs: [[ 
                    credentialsId: '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',
                    url: 'https://github.com/meyarroum/myapp.git']]])
}

            }
        }


       stage('Install') {
             steps{
                script{
                    sh "sudo npm install"
                }
            }
        }



       stage ('Build') {
            steps {
               script {
               sh "ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml "
                
}

            }
        }


       stage ('docker') {
            steps {
               script {
               sh "ansible-playbook Ansible/docker.yml -i Ansible/inventory/host.yml "
                
}

            }
        }



 }
}

