
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

    stage('deploy') {
        steps {
            sh 'node index.js'
        }
    }
  }

}