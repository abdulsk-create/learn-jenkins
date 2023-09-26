pipeline {
    //agent any
    agent { node { label 'workstation' } }

    environment {
      TEST_URL = "entertanova.com"
    }
    stages {

        stage('Compile') {
            steps {
              //echo 'hello world'
              //error 'this is an error'
              echo TEST_URL
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

