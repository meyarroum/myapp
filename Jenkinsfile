pipeline {

    agent any


    stages {


       stage ('Pull') {
            steps {
               script {
               checkout([$class: 'GitSCM', branches: [[name: '*/master']],
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

