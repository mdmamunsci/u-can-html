
pipeline {

  agent any

  stages {
    stage('checkout') {
        steps {
            checkout scm
        }
    }

    stage('test') {
        steps {
            sh 'pwd'
        }
    }

    stage('Debug') {
        steps {
            sh 'echo $PATH'          // Check if Docker's path is included
            sh 'which docker'        // Locate Docker executable
            sh 'docker --version'    // Confirm Docker availability
            sh 'docker ps'    // Confirm Docker availability
        }
    }

    stage('deploy') {
        steps {
            sh 'pwd'
        }
    }
  }

}
