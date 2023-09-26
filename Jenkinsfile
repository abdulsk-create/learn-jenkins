pipeline {
    //agent any
    agent { node { label 'workstation' } }

    environment {
      TEST_URL = "entertanova.com"
      SSH = credentials("centos-ssh")
    }

    options {
            ansiColor('xterm')
        }

    parameters {
      string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

      text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

      booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

      choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

      password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    //
    triggers { pollSCM('*/1 * * * *') }

    stages {

        stage('Compile') {
            steps {
              //echo 'hello world'
              //error 'this is an error'
              echo TEST_URL
              echo SSH
              sh 'env'
              sh 'ansible -i 172.31.83.86, all -e ansible_user=${SSH_USR} -e ansible_password=${SSH_PSW} -m ping'
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

