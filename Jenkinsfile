pipeline {
    //agent any
    agent { node { label 'workstation' } }

    environment {
      TEST_URL = "entertanova.com"
      SSH = credentials("centos-ssh")
    }
    stages {

        stage('Compile') {
            steps {
              //echo 'hello world'
              //error 'this is an error'
              echo TEST_URL
              echo SSH
              sh 'env'
              sh 'ansible -i 172.31.83.86, all -e ansible_user${SSH_USR} -e ansible_password${SSH_PSW} -m ping'
            }
        }

    }
    post {
      always {
        echo 'post'
        // send email
        // trigger job
        // update jira status about the latest build


      }
    }
}

